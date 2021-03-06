---
TOCTitle: Determine Where to Store WSUS Updates
Title: Determine Where to Store WSUS Updates
ms:assetid: 'aa4d106e-830e-4074-8675-bc52b2ada094'
ms:contentKeyID: 18142270
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc708543(v=WS.10)'
---

Determine Where to Store WSUS Updates
=====================================

Although metadata that describes updates is stored in the WSUS database, the updates themselves are not. Updates are divided into two parts: a metadata part that describes the update, and the files required to install the update on a computer. Update metadata includes the end-user license agreement (EULA) and is typically much smaller than the size of the actual update

You have two choices for update locations. You can store updates on the local WSUS server, or you can store updates on Microsoft Update. There is a configuration using shared update storage for network load balanced clusters, described in [Appendix C: Configure WSUS for Network Load Balancing](https://technet.microsoft.com/b17d7555-81fd-4e32-8e8b-92b4c7922116). The result for either option is outlined in the following sections. If you have multiple WSUS servers chained together, each WSUS server in the chain may choose its own update storage options. These options are selected during the setup process, but can also be changed after installing WSUS. See [Advanced Synchronization Options](https://technet.microsoft.com/65d4cddd-8de0-477f-833d-ce5e2422eef0) for step-by-step procedures.

Local storage
-------------

You can store update files locally on the WSUS server. This saves bandwidth on your Internet connection because client computers download updates directly from the WSUS server. This option requires enough disk space to store the updates you intend to download. There is a minimum requirement of 20 GB of hard disk space to store updates locally, but 30 GB is recommended. Local storage is the default option.

| ![](images/Cc708543.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                         |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| The 30 GB recommendation is only an estimate based on a number of variables, such as the number of updates released by Microsoft for any given product, how many products and update languages are selected, and whether standard update files or express updates are to be downloaded. Although 30 GB should work for most customers, your particular situation might require more than 30 GB of disk space. |

Remote storage
--------------

If you want, you can store update files remotely on Microsoft servers. WSUS enables you to use Microsoft Update for the distribution of approved updates throughout your organization. This is particularly useful if most of the client computers connect to the WSUS server over a slow WAN connection but have high-bandwidth connections to the Internet, or if there are only a small number of client computers.

![](images/Cc708543.9f6269a7-ae94-426d-be4d-7238d4fe0e78(WS.10).gif)

In this scenario WSUS is configured so that client computers download updates from Microsoft Update. When you synchronize the WSUS server with Microsoft Update, you get only the update metadata describing the updates. The files that install updates on client computers are not stored on the WSUS server.

Updates are still approved on the WSUS server, but each client connects to the Internet to download the approved updates from Microsoft servers. These are the same servers Microsoft uses to distribute updates to the public. Although your clients obtain updates from Microsoft over the Internet, you still make the decisions about which updates are approved for distribution. The advantage of this scenario is faster downloads for distributed clients and network bandwidth savings for your organization.
