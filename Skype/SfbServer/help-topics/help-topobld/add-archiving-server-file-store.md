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
# <a name="add-archiving-server-file-store"></a>Aggiungere archivio file per il server di archiviazione

Per abilitare l'archiviazione del contenuto dei messaggi istantanei e delle conferenze Web (riunioni), è necessario specificare una condivisione file da usare come archivio file delle copie di tutto il contenuto delle conferenze Web. È possibile usare una condivisione file esistente per l'archivio file oppure specificare una nuova condivisione file indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file e un nome di cartella per la nuova condivisone file.

> [!IMPORTANT]
> È possibile specificare la condivisione file in Generatore di topologie prima di crearla, ma è necessario creare la condivisione file nella posizione definita prima di pubblicare la topologia. > quando si aggiunge un server di archiviazione alla topologia, il generatore di topologie deve essere in grado di impostare l'archivio file di archiviazione e di configurare gli elenchi di controllo di accesso discrezionale sulla condivisione file da utilizzare per l'archivio file. Quando si esegue Generatore di topologie per pubblicare la nuova topologia, è quindi necessario essere connessi con un account dotato delle autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file.

Per informazioni dettagliate sul supporto dell'archiviazione per le condivisioni file, vedere [file Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) nella documentazione relativa alla supportabilità e [SQL Server Data and log file Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sulla collocazione della condivisione file, vedere [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) nella documentazione relativa alla supportabilità.


