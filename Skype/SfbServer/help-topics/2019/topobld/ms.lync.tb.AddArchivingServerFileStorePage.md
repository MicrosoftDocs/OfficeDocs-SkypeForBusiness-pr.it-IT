---
title: Aggiungere l'archivio file per il server di archiviazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: Per abilitare l'archiviazione del contenuto dei messaggi istantanei e delle conferenze Web (riunioni), è necessario specificare una condivisione file da usare come archivio file delle copie di tutto il contenuto delle conferenze Web. È possibile usare una condivisione file esistente per l'archivio file oppure specificare una nuova condivisione file indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisone file.
ms.openlocfilehash: 2e8c4ac23ce68eab111bbb7775eec23aba2f12d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100232"
---
# <a name="add-archiving-server-file-store"></a>Aggiungere archivio file per il server di archiviazione

Per abilitare l'archiviazione del contenuto dei messaggi istantanei e delle conferenze Web (riunioni), è necessario specificare una condivisione file da usare come archivio file delle copie di tutto il contenuto delle conferenze Web. È possibile usare una condivisione file esistente per l'archivio file oppure specificare una nuova condivisione file indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisone file.

> [!IMPORTANT]
> È possibile specificare la condivisione file in Generatore di topologie prima di crearla, ma è necessario creare la condivisione file nella posizione definita prima di pubblicare la topologia. > Quando si aggiunge un server di archiviazione alla topologia, Generatore di topologie deve essere in grado di configurare l'archivio file di archiviazione e configurare gli elenchi di controllo di accesso discrezionale (DACL) nella condivisione file da utilizzare per l'archivio file. Quando si esegue Generatore di topologie per pubblicare la nuova topologia, è quindi necessario essere connessi con un account dotato delle autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file.

Per informazioni dettagliate sul supporto dell'archiviazione per le condivisioni file, vedere [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) nella documentazione relativa alla supportabilità e SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulla collocazione della condivisione file, vedere [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) nella documentazione relativa alla supportabilità.