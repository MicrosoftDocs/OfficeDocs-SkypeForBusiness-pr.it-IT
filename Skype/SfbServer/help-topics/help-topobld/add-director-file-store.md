---
title: Aggiungere l'archivio file per il Director
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
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: È necessario specificare una condivisione file da usare come archivio file per i Director. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisione file.
ms.openlocfilehash: 2c7ad609ea3e58f0368f8c1e3d8716223aa68700
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824286"
---
# <a name="add-director-file-store"></a>Aggiungere l'archivio file per il Director

È necessario specificare una condivisione file da usare come archivio file per i Director. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisione file.

> [!IMPORTANT]
> Quando si aggiungono Director a una topologia, per la pubblicazione della topologia è necessario un accesso appropriato per impostare l'archivio file e configurare elenchi di controllo di accesso discrezionale (DACL) nella condivisione file da usare per l'archivio file. Quando si esegue Generatore di topologie e si pubblica la nuova topologia, è quindi necessario essere connessi con un account che abbia le autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file.

Per informazioni dettagliate sul supporto dell'archiviazione per le condivisioni file, vedere [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) nella documentazione relativa alla supportabilità e SQL Server Data and Log File [Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulla collocazione della condivisione file, vedere [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) nella documentazione relativa al supporto. Per informazioni dettagliate sulla progettazione della topologia per i Director, vedere [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) nella documentazione relativa alla distribuzione.


