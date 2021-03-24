---
title: Aggiungere l'archivio file per il Director
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: È necessario specificare una condivisione file da usare come archivio file per i Director. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisione file.
ms.openlocfilehash: 56fb33653f2f463e9b336ae447a1c665680ed6df
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100142"
---
# <a name="add-director-file-store"></a>Aggiungere l'archivio file per il Director

È necessario specificare una condivisione file da usare come archivio file per i Director. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisione file.

> [!IMPORTANT]
> Quando si aggiungono Director a una topologia, per la pubblicazione della topologia è necessario un accesso appropriato per impostare l'archivio file e configurare elenchi di controllo di accesso discrezionale (DACL) nella condivisione file da usare per l'archivio file. Quando si esegue Generatore di topologie e si pubblica la nuova topologia, è quindi necessario essere connessi con un account che abbia le autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file.

Per informazioni dettagliate sul supporto dell'archiviazione per le condivisioni file, vedere [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) nella documentazione relativa alla supportabilità e SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulla collocazione della condivisione file, vedere [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) nella documentazione relativa al supporto. Per informazioni dettagliate sulla progettazione della topologia per i Director, vedere [Define a Single Director in Topology Builder](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology) nella documentazione relativa alla distribuzione.