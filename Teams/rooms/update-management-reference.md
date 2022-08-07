---
title: riferimento Microsoft Teams Rooms
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Materiale di riferimento
f1keywords: ''
ms.openlocfilehash: e75742cb209018030ca9d6600c518e210b396386
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268411"
---
# <a name="managing-room-software-stack"></a>Gestione dello stack di software per sale  
In ogni stanza, diverse parti dello stack software lavorano tutte insieme per offrire l'esperienza. Ad alto livello, possono essere riassunti nel modo seguente: 

![Screenshot del riepilogo dello stack di software](../media/update-management-006.jpg)

Per garantire un'esperienza di riunione positiva ogni giorno in ogni sala, è importante **standardizzare ogni componente software** in esecuzione in ognuna delle sale e implementare le correzioni nelle sale a seconda della configurazione. È anche comune che i clienti configurino il proprio processo di convalida per acquisire fiducia su eventuali correzioni in sospeso verificando che risolve davvero un problema che potrebbero riscontrare o le funzionalità di anteprima per preparare l'organizzazione per la modifica.  

Managed Services for Microsoft Teams Rooms gestisce tutti gli elementi precedenti in modo da non doversi preoccupare di ottenere un aggiornamento o risolvere i problemi relativi a un aggiornamento. In questa sezione verrà descritto il funzionamento degli aggiornamenti software gestiti.  

## <a name="managing-to-a-good-state"></a>Gestione di uno stato di buono stato 
Il nostro obiettivo principale è mantenere le sale in esecuzione e disponibili per la tua organizzazione. Gli esperti di Servizi gestiti lavorano costantemente per conto dell'utente per curare, convalidare e distribuire gli aggiornamenti nelle sale di produzione. In alcuni casi, è possibile che l'integrità della stanza venga assegnata in ordine di priorità rispetto alle nuove funzionalità e versioni da convalidare prima che vengano distribuite.

Soprattutto, significa che non devi preoccuparti di investire tempo per imparare i dettagli di questi aggiornamenti e convalidarli manualmente. Se si verificano problemi con un aggiornamento specifico e con qualsiasi chat room specifica, microsoft collaborerà per risolverli.  

Di conseguenza, il processo di distribuzione degli aggiornamenti può essere suddiviso in:

- Il team di Servizi gestiti identificherà in modo proattivo gli aggiornamenti, li convaliderà e li promuovi per il rilascio nell'ambiente.
- Aggiornamenti consegnate ai gruppi verranno ordinate per evitare conflitti e interazioni pianificate per evitare le normali ore di attività.
- Il sistema di anello offre la possibilità di essere a conoscenza degli aggiornamenti applicati alle stanze senza che tu faccia alcun lavoro.
- I servizi gestiti monitoreranno gli aggiornamenti e avviseranno automaticamente il centro operativo della sala per il monitoraggio dei problemi e collaboreranno con l'utente per risolverli.
