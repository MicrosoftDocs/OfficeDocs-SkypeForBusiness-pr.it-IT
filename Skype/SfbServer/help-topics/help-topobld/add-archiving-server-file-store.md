---
title: Aggiungere l'archivio file per il server di archiviazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Per abilitare l'archiviazione del contenuto dei messaggi istantanei e delle conferenze Web (riunioni), è necessario specificare una condivisione file da usare come archivio file delle copie di tutto il contenuto delle conferenze Web. È possibile usare una condivisione file esistente per l'archivio file oppure specificare una nuova condivisione file indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisone file.
ms.openlocfilehash: a35bf3f7c1ef066aec1139ab2e886073ab65e23b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807146"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="9e6d8-104">Aggiungere archivio file per il server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="9e6d8-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="9e6d8-p102">Per abilitare l'archiviazione del contenuto dei messaggi istantanei e delle conferenze Web (riunioni), è necessario specificare una condivisione file da usare come archivio file delle copie di tutto il contenuto delle conferenze Web. È possibile usare una condivisione file esistente per l'archivio file oppure specificare una nuova condivisione file indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisone file.</span><span class="sxs-lookup"><span data-stu-id="9e6d8-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e6d8-107">È possibile specificare la condivisione file in Generatore di topologie prima di crearla, ma è necessario creare la condivisione file nella posizione definita prima di pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9e6d8-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="9e6d8-108">> quando si aggiunge un server di archiviazione alla topologia, il generatore di topologie deve essere in grado di impostare l'archivio file di archiviazione e di configurare gli elenchi di controllo di accesso discrezionale sulla condivisione file da utilizzare per l'archivio file.</span><span class="sxs-lookup"><span data-stu-id="9e6d8-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="9e6d8-109">Quando si esegue Generatore di topologie per pubblicare la nuova topologia, è quindi necessario essere connessi con un account dotato delle autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="9e6d8-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="9e6d8-110">Per informazioni dettagliate sul supporto dell'archiviazione per le condivisioni file, vedere [file Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) nella documentazione relativa alla supportabilità e [SQL Server Data and log file Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9e6d8-110">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="9e6d8-111">Per informazioni dettagliate sulla collocazione della condivisione file, vedere [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="9e6d8-111">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


