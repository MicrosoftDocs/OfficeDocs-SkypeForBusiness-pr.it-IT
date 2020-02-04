---
title: Aggiungere l'archivio file per il server di archiviazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Per abilitare l'archiviazione del contenuto dei messaggi istantanei e delle conferenze Web (riunioni), è necessario specificare una condivisione file da usare come archivio file delle copie di tutto il contenuto delle conferenze Web. È possibile usare una condivisione file esistente per l'archivio file oppure specificare una nuova condivisione file indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisone file.
ms.openlocfilehash: 72f8ad131d016d9e14e556b6618ba837a02c7d27
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685379"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="199d4-104">Aggiungere l'archivio file per il server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="199d4-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="199d4-p102">Per abilitare l'archiviazione del contenuto dei messaggi istantanei e delle conferenze Web (riunioni), è necessario specificare una condivisione file da usare come archivio file delle copie di tutto il contenuto delle conferenze Web. È possibile usare una condivisione file esistente per l'archivio file oppure specificare una nuova condivisione file indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisone file.</span><span class="sxs-lookup"><span data-stu-id="199d4-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="199d4-107">È possibile specificare la condivisione file in Generatore di topologie prima di crearla, ma è necessario creare la condivisione file nella posizione definita prima di pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="199d4-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="199d4-108">> quando si aggiunge un server di archiviazione alla topologia, generatore di topologie deve essere in grado di configurare l'archivio file di archiviazione e configurare elenchi di controllo di accesso discrezionale (DACL) nella condivisione file da usare per l'archivio file.</span><span class="sxs-lookup"><span data-stu-id="199d4-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="199d4-109">Quando si esegue Generatore di topologie per pubblicare la nuova topologia, è quindi necessario essere connessi con un account dotato delle autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="199d4-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="199d4-p104">Per informazioni dettagliate sul supporto per l'archiviazione per condivisioni file, vedere [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) nella documentazione relativa alla supportabilità e [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulla collocazione della condivisione file, vedere [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="199d4-p104">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation. For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


