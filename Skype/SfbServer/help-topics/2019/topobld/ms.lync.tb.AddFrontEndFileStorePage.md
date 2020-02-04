---
title: Aggiungere l'archivio file per Front End Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile utilizzare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve essere posizionata la condivisione file, oltre a un nome di cartella per la nuova condivisione file.
ms.openlocfilehash: 7bfcf204a16468b1de7a24e1f6eee8c611bb2da8
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702951"
---
# <a name="add-front-end-file-store"></a>Aggiungere l'archivio file per Front End Server

È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile utilizzare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve essere posizionata la condivisione file, oltre a un nome di cartella per la nuova condivisione file.

> [!IMPORTANT]
> La condivisione file non può essere posizionata nel server Enterprise Edition Front End Server, ma può essere posizionata in un server Standard Edition.

> [!IMPORTANT]
> È possibile definire la condivisione file in Generatore di topologie prima di crearla, ma è necessario crearla nel percorso definito prima di pubblicare la topologia.

> [!IMPORTANT]
> Quando si aggiunge un pool Enterprise Edition Front End o un server Standard Edition alla topologia, il Generatore di topologie deve essere in grado di impostare l'archivio file e configurare elenchi di controllo di accesso discrezionale (DACL) nella condivisione file da usare per l'archivio file. Quando si esegue il Generatore di topologie per pubblicare la nuova topologia, è pertanto necessario essere connessi con un account dotato delle autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file.

Per informazioni dettagliate sul supporto dell'archiviazione per le condivisioni file, vedere [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) nella documentazione relativa alla supportabilità e [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulla collocazione della condivisione file, vedere [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) nella documentazione relativa alla supportabilità. Per informazioni dettagliate sulla progettazione della topologia per un pool Enterprise Edition Front End, vedere [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) nella documentazione relativa alla distribuzione.


