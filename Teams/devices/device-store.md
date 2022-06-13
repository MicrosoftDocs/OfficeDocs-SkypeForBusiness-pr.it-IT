---
title: Teams store di dispositivi
ms.author: dstrome
author: dstrome
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
description: Scopri come esplorare e acquistare dispositivi nello store dei dispositivi dell'interfaccia di amministrazione di Teams
ms.openlocfilehash: e5cedb84d50111d90d90d47802f667fb6fdbc106
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045645"
---
# <a name="purchase-devices-in-the-teams-device-store"></a>Acquistare dispositivi nello store dei dispositivi Teams

>[!NOTE]
>L'archivio Teams dispositivi è attualmente disponibile solo in **anteprima pubblica**. L'anteprima pubblica consente di testare le funzionalità imminenti e fornire feedback. Le funzionalità incluse nell'anteprima pubblica potrebbero non essere complete, potrebbero essere soggette a modifiche e non sono supportate in Office 365 Government Cloud.

Lo store dei dispositivi nell'interfaccia di amministrazione di Teams consente di esplorare, acquistare ed effettuare il provisioning dei dispositivi certificati per Microsoft Teams.  

 Per usare l'archivio dispositivi nell'interfaccia di amministrazione di Teams, vai a **Dispositivi > Store**.

## <a name="requirements"></a>Requisiti

Per usare l'archivio dispositivi, è necessario essere un amministratore globale o un amministratore Teams.

## <a name="browse-the-store"></a>Esplora lo Store

L'archivio dispositivi include tutti i dispositivi certificati per Teams, inclusi auricolari, fotocamere Web e dispositivi Teams come Teams Rooms, telefoni da tavolo e schermi Teams. È possibile ordinare, filtrare o eseguire ricerche per trovare il dispositivo necessario all'organizzazione.

## <a name="purchase-devices"></a>Acquista dispositivi

Quando si acquistano dispositivi dallo store del dispositivo, il pagamento e l'evasione dei pagamenti, inclusa la spedizione e la consegna, vengono gestiti da UnifiedCommunications.com, un partner di evasione dei dati di terze parti Microsoft.  

Puoi pagare con una carta di credito o un ordine d'acquisto. Il pagamento dell'ordine di acquisto richiede la configurazione una tantum con il provider di evasione ordini.

Tutti gli ordini possono essere restituiti fino a 30 giorni dopo la consegna.

## <a name="data-handling-and-sharing"></a>Gestione e condivisione dei dati

L'archivio Teams dispositivi deve condividere le informazioni di base su utenti e società, inclusi i GUID di utenti e tenant, con UnifiedCommunications.com per consentire l'acquisto nell'interfaccia di amministrazione di Teams.

La condivisione dei dati è disattivata per impostazione predefinita. Per abilitarla, vai all'archivio Teams dispositivi, seleziona l'icona delle impostazioni e attiva l'impostazione.  

Quando questa impostazione è disattivata, i dati non verranno condivisi e potrai esplorare lo store dei dispositivi Teams, ma non potrai effettuare acquisti. I dati raccolti e condivisi con il provider di evasione dei dati mentre l'impostazione era attivata vengono elaborati come specificato nella loro informativa sulla privacy.

## <a name="order-tracking-and-history"></a>Monitoraggio e cronologia degli ordini

Puoi visualizzare la cronologia degli ordini in **Store > Cronologia ordini**, che include tutti gli ordini effettuati da te e da altri amministratori dell'organizzazione. La cronologia ordini include anche lo stato della spedizione dei tuoi ordini. Per domande su verifica dell'ordine, resi o rimborsi, contatta UnifiedCommunications.com. Le informazioni di contatto sono disponibili nella pagina Cronologia ordini.

Gli ordini effettuati nell'archivio Teams dispositivo e i dati associati vengono classificati come ordini tenant e dati del tenant.

## <a name="provision-devices"></a>Effettuare il provisioning dei dispositivi

Quando si acquistano dispositivi che supportano il provisioning remoto, l'indirizzo MAC di tali dispositivi viene aggiunto automaticamente all'interfaccia di amministrazione di Teams quando il dispositivo viene spedito. A seconda dell'ordine e della data di spedizione, possono essere necessari circa 5 giorni prima che l'indirizzo MAC venga visualizzato nell'interfaccia di amministrazione di Teams.

Una volta forniti i dispositivi, vedi [Effettuare il provisioning remoto dei dispositivi](remote-provision-remote-login.md#generate-a-verification-code) per completare il processo di provisioning e accesso.
