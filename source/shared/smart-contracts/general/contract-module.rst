.. _contract-module:

======================
Smart contract modules
======================

Smart contracts are deployed on the chain in *smart contract modules*.

.. note::

   A smart contract module is often referred to simply as a *module*.

A module can contain one or more smart contracts, allowing code to be shared
among the contracts and can optionally contain :ref:`contract schemas
<contract-schema>`.

.. graphviz::
   :align: center
   :caption: A smart contract module containing two smart contracts.

   digraph G {
       subgraph cluster_0 {
           node [fillcolor=white, shape=note]
           label = "Module";
           "Crowdfunding";
           "Escrow";
       }
   }

The module must be self-contained, and only have a restricted list of imports
that allow for interaction with the chain.
These are provided by the host environment and are available for the smart
contract by importing a module named ``concordium``.

.. seealso::

   Check out :ref:`host-functions` for a complete reference.

On-chain language
=================

On the Concordium blockchain the smart contract language is a subset of `Web
Assembly`_ (Wasm in short) which is designed to be a portable compilation
target and to be run in sandboxed environments. This is useful because smart
contracts will be run by bakers in the network who do not necessarily trust
the code.

Wasm is a low-level language and it is impractical to write by hand. Instead one
can write smart contracts in a more high-level language which is then
compiled to Wasm.

.. _wasm-limitations:

Limitations
-----------

.. todo::

   Add other limitations, such as start sections...

The blockchain environment is very particular in the sense that each node must
be able to execute the contract in exactly the same way, using exactly the same
amount of resources. Otherwise nodes would fail to reach consensus on the
state of the chain. For this reason smart contracts need to be written in a restricted
subset of Wasm.

Floating point numbers
^^^^^^^^^^^^^^^^^^^^^^

Although Wasm does have support for floating point numbers, a smart contract is
disallowed to use them. The reason for this is that Wasm floating-point numbers
can have a special ``NaN`` ("not a number") value whose treatment can result in nondeterminism.

The restriction applies statically, meaning that smart contracts cannot contain
floating point types, nor can they contain any instructions that involve floating
point values.


Deployment
==========

Deploying a module to the chain means submitting the module bytecode as a
transaction to the Concordium network. If *valid* this transaction will be
included in a block. This transaction, as every other transaction, has an
associated cost. The cost is based on the size of the bytecode and is charged
for both checking validity of the module and on-chain storage.

The deployment itself does not execute
smart contract. To execute, a user must first create an *instance* of a contract.

.. seealso::

   See :ref:`contract-instances` for more information.

.. _smart-contracts-on-chain:

.. _smart-contracts-on-the-chain:

.. _contract-on-chain:

.. _contract-on-the-chain:

Smart contract on the chain
===========================

A smart contract on the chain is a collection of functions exported from a deployed
module. The concrete mechanism used for this is the `Web Assembly`_ export
section. A smart contract must export one function for initializing new
instances and can export zero or more functions for updating the instance.

Since a smart contract module can export functions for multiple different smart
contracts, we associate the functions using a naming scheme:

- ``init_<contract-name>``: The function for initializing a smart contract must
  start with ``init_`` followed by a name of the smart contract. The contract
  must consist only of ASCII alphanumeric or punctuation characters, and is not
  allowed to contain the ``.`` symbol.

- ``<contract-name>.<receive-function-name>``: Functions for interacting with a
  smart contract are prefixed with the contract name, followed by a ``.`` and a
  name for the function. Same as for the init function, the contract name is not allowed
  to contain the ``.`` symbol.

.. note::

   The function name is limited to 100 bytes. The whole function name must be ASCII alphanumeric and punctuation, not just the contract name.

.. note::

   If you develop smart contracts using Rust and ``concordium-std``, the
   procedural macros ``#[init(...)]`` and ``#[receive(...)]`` set up the
   correct naming scheme.

.. _Web Assembly: https://webassembly.org/
