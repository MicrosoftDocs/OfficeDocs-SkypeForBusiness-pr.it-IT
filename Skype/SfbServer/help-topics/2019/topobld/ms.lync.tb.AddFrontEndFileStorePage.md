---
title: Aggiungere l'archivio file per Front End Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile utilizzare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve essere posizionata la condivisione file, oltre a un nome di cartella per la nuova condivisione file.
ms.openlocfilehash: 90860ff365ff1d5ff2279dc32df96f77d9725c895c7587f9606ccfab21364668
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54317621"
---
# <a name="add-front-end-file-store"></a>Aggiungere l'archivio file per Front End Server

È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile utilizzare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve essere posizionata la condivisione file, oltre a un nome di cartella per la nuova condivisione file.

> [!IMPORTANT]
> La condivisione file non può essere posizionata edizione Enterprise Front End Server, ma può trovarsi in un server edizione Standard server.

> [!IMPORTANT]
> È possibile definire la condivisione file nel Generatore di topologie prima di crearla, ma è necessario crearla nel percorso definito prima di pubblicare la topologia.

> [!IMPORTANT]
> Quando si aggiunge un pool Enterprise Edition Front End o un server Standard Edition alla topologia, il Generatore di topologie deve essere in grado di impostare l'archivio file e configurare elenchi di controllo di accesso discrezionale (DACL) nella condivisione file da usare per l'archivio file. Quando si esegue il Generatore di topologie per pubblicare la nuova topologia, è pertanto necessario essere connessi con un account dotato delle autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file.

Per informazioni dettagliate sul supporto dell'archiviazione per le condivisioni file, vedere [File Archiviazione Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) nella documentazione relativa alla supportabilità e SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulla collocazione della condivisione file, vedere [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) nella documentazione relativa al supporto. Per informazioni dettagliate sulla progettazione della topologia per un pool Enterprise Edition Front End, vedere [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) nella documentazione relativa alla distribuzione.