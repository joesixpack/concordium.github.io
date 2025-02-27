.. _account-recovery-desktop:

=====================
Account recovery
=====================

.. contents::
    :local:
    :backlinks: none
    :depth: 1

Recover accounts in the Desktop Wallet without a backup file
============================================================

If, for some reason, you've lost one or more of your accounts in the Desktop Wallet, and you've also lost the backup file, you can use the Ledger device to recover those accounts.

You only have to perform a recovery if you have lost the backup of your accounts and identities. If you still have the backup file, you can import the accounts back into the Desktop Wallet. To learn more about making backups of your data, see :ref:`Make a backup of identities, accounts, and addresses <export-import-desktop>`.

If you've lost your Ledger device or the device has stopped working, you can restore the keys in another Ledger device by by restoring it from the recovery phrase used for the original device. To learn more about the recovery phrase of a Ledger device, see Ledger's documentation:
`What is a recovery phrase <https://www.ledger.com/academy/crypto/what-is-a-recovery-phrase/>`_ .


How the recovery process works
------------------------------

When you create a new identity in the Desktop Wallet, a number on the Ledger is associated with the identity. This is called the identity index and there can be more identity indices on a Ledger. These indices are used sequentially, so the first identity created from a Ledger uses index *0*, the next uses index *1*, and so on.

The Ledger stores data about the credentials that belong to an identity. The keys you use to sign account transactions are all attached to credentials. It’s the credentials on an account that determine who’s allowed to sign transactions. To learn more about identities, see :ref:`Identities and accounts <reference-id-accounts>`.

Lost identities can't be recovered because the identity object is not stored on the Ledger. However, you can go through each index on the Ledger where the data to create credentials are stored and use this information to regain access to the accounts related to a given identity.

For each identity index, the recovery process uses the Ledger device to calculate the IDs of the credentials, which also have sequential indices. The wallet then checks on the blockchain whether the credentials have been deployed, and which account each credential is attached to. These accounts are then added to the Desktop Wallet along with the deployed credentials.

If all your identity issuances were successful, you can stop the recovery when you encounter an unused index. However, if one of your identity issuance processes failed, this might have caused an index to be skipped. Therefore, you must determine yourself when the recovery is completed.

The recovery also creates placeholders for the missing identities to indicate that the index has already been used. However, the information used to create new accounts and credentials on a missing identity can't be recovered because it doesn't exist on the blockchain. That's why you can't create new accounts using these placeholders. Instead, you can request a new identity from an identity provider.

The names of the accounts and the notes on the credentials are also not recoverable because they are only saved locally.

Incomplete backups
---------------------

If you have :ref:`imported <export-import-desktop>` accounts from a backup file and you know there are accounts missing on one or more identities, you can go through the recovery process to recover the missing accounts.

How to recover accounts
=======================

#. In the **Desktop Wallet**, go to **Settings**, and then select **Recover existing accounts**.

#. Familiarize yourself with the recovery information, and then select **Continue**.

#. Connect the Ledger to the computer if you haven't done so already, and then select **Submit**.

#. In the Desktop Wallet, there's a message saying *Please allow recovering credentials*. The Ledger says *Recover credentials*. In the right pane, you can see the indices that are found, and the accounts, if any, associated with each index.

#. When you consider the recovery complete, select **Stop recovery, I found all my accounts**. You then see an overview of all the recovered accounts. If you don't think the recovery is complete, you can go back and continue the recovery process.

#. To view the recovered accounts, go to **Accounts**. A recovered account doesn't have the name you originally gave it. Instead the name consists of the first eight digits of the account address. Furthermore, because the identities are not recovered, the accounts show the index number that's associated with the identity and not the identity itself.

#. To view placeholders for identities, go to **Identities**. Here you can see placeholders for the missing identities. These placeholders show the index numbers that have been used. You can't use the placeholders to create new accounts.

