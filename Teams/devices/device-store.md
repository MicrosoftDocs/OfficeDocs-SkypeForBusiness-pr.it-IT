---
title: Teams dispositivo
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: rahulimi
ms.topic: article
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
description: Informazioni su come esplorare e acquistare dispositivi nell'Teams dell'interfaccia di amministrazione
ms.openlocfilehash: cf67b4e99dabab45dec5cb46ca3996a15183d66a
ms.sourcegitcommit: 42c355d3f4bbe52c063b8f2119baefc0b88f9563
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2022
ms.locfileid: "64404070"
---
# <a name="purchase-devices-in-the-teams-device-store"></a>Acquistare dispositivi nello store Teams dispositivi

>[!NOTE]
>L Teams archivio dispositivi è attualmente disponibile solo **nell'anteprima pubblica**. L'anteprima pubblica consente di testare le funzionalità imminenti e fornire feedback. Le funzionalità incluse nell'anteprima pubblica potrebbero non essere complete, potrebbero subire modifiche e non sono supportate in Office 365 Government Cloud.

L'archivio dispositivi nell'Teams di amministrazione consente di esplorare, acquistare ed eseguire il provisioning di dispositivi certificati per Microsoft Teams.  

 Per usare l'archivio dispositivi nell'Teams di amministrazione, passare **a Dispositivi > Store**.

## <a name="requirements"></a>Requisiti

Per usare l'archivio dispositivi, è necessario essere un amministratore globale, un amministratore Teams o un amministratore Teams dispositivo.

## <a name="browse-the-store"></a>Esplorare lo store

L'archivio dispositivi include tutti i dispositivi certificati per Teams, inclusi cuffie, videocamere Web e dispositivi Teams come Teams Rooms, telefoni da tavolo e schermi Teams. È possibile ordinare, filtrare o cercare il dispositivo necessario per l'organizzazione.

## <a name="purchase-devices"></a>Acquistare dispositivi

Quando si acquistano dispositivi dallo store di dispositivi, il pagamento e l'adempimento, tra cui la spedizione e la consegna, vengono gestiti da UnifiedCommunications.com, un partner microsoft di terze parti.  

È possibile pagare con una carta di credito o un ordine di acquisto. Il pagamento dell'ordine di acquisto richiede l'installazione una sola volta con il provider di adempimento.

Tutti gli ordini possono essere restituiti fino a 30 giorni dopo la consegna.

## <a name="data-handling-and-sharing"></a>Gestione e condivisione dei dati

L'archivio Teams dispositivo deve condividere le informazioni di base su utenti e società, inclusi i GUID utente e tenant, con UnifiedCommunications.com per abilitare gli acquisti nell'interfaccia di amministrazione Teams lavoro.

La condivisione dei dati è disattivata per impostazione predefinita. Per abilitarlo, vai all'Teams dei dispositivi, seleziona l'icona delle impostazioni e attiva gestione e condivisione dei dati.  

Quando questa impostazione è disattivata, i dati non verranno condivisi ed è possibile esplorare l'archivio Teams dispositivi, ma non è possibile effettuare acquisti. I dati raccolti e condivisi con il provider di adempimento mentre l'impostazione era attivata vengono elaborati come specificato nell'informativa sulla privacy.

## <a name="order-tracking-and-history"></a>Tracciabilità e cronologia degli ordini

Per visualizzare la cronologia degli ordini, accedere a **Store > Cronologia ordini**, che include tutti gli ordini effettuati dall'utente e da altri amministratori dell'organizzazione. La cronologia degli ordini include anche lo stato di spedizione degli ordini. Per domande sulla verifica degli ordini, i resi o i rimborsi, contattare UnifiedCommunications.com. Le informazioni di contatto sono disponibili nella pagina Cronologia ordini.

Gli ordini effettuati nell'archivio Teams dispositivo e tutti i dati ad essi associati vengono classificati come ordini di tenant e dati del tenant.

## <a name="provision-devices"></a>Eseguire il provisioning dei dispositivi

Quando si acquistano dispositivi che supportano il provisioning remoto, l'indirizzo MAC di tali dispositivi viene aggiunto automaticamente all'interfaccia di amministrazione di Teams quando il dispositivo viene spedito. A seconda dell'ordine e della data di spedizione, possono essere necessario circa 5 giorni prima che l'indirizzo MAC venga visualizzato in TAC.

Dopo il recapito dei dispositivi, vedere Eseguire il [provisioning](remote-provision-remote-login.md#generate-a-verification-code) remoto dei dispositivi per completare il provisioning e il processo di accesso.
