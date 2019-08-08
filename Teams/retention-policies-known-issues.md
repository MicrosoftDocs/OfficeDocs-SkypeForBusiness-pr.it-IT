---
title: Problemi noti per i criteri di conservazione in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Elenco corrente dei problemi noti per i criteri di conservazione di Microsoft teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b13fc5347338b28c877b224f758c79513e379391
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243609"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Problemi noti per i criteri di conservazione in Microsoft Teams

Di seguito sono riportati i problemi noti per i criteri di conservazione in team che vengono rilevati e analizzati.

- In Scegli teams nella riga location messages Channel teams è possibile che i gruppi di Office 365 non siano anche teams. Questa operazione verrà affrontata in futuro.

- In Scegli utenti nella riga posizione chat teams è possibile che vengano visualizzati utenti guest e non-Mailbox. I criteri di conservazione non sono pensati per essere impostati per gli utenti e stiamo lavorando per rimuoverli dall'elenco.

- Il programma ELC (Exchange Life Cycle Assistant) viene eseguito giornalmente, ma ha uno SLA di 7 giorni. Di conseguenza, è possibile che, se si dispone di un criterio di conservazione di teams per eliminare gli elementi precedenti a 60 giorni, questi elementi potrebbero essere mantenuti per un massimo di 67 giorni. Non si tratta di una nuova situazione: segue il modello Exchange. Naturalmente, nella maggior parte dei casi, non ci sono ritardi.


| | | |
|---------|---------|---------|
|![Icona che rappresenta un punto decisionale](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Punto decisionale         |Quali caratteristiche di sicurezza e conformità richiedono l'organizzazione? L'organizzazione ha le licenze necessarie per soddisfare i requisiti aziendali per la sicurezza e la conformità?         |
|![Icona che rappresenta i passaggi successivi](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Passaggi successivi         |Documentare le caratteristiche di sicurezza e conformità richieste.         |
