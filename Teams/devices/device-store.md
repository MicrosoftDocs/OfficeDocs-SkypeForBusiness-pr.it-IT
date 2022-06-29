---
title: Store di dispositivi di Teams
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
description: Informazioni su come esplorare e acquistare dispositivi nello store dei dispositivi dell'interfaccia di amministrazione di Teams
ms.openlocfilehash: 9e555cd0f389c8158e66b824183a1038fc11ce04
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240715"
---
# <a name="purchase-devices-in-the-teams-device-store"></a>Acquistare dispositivi nello Store dei dispositivi di Teams

Lo store dei dispositivi nell'interfaccia di amministrazione di Teams consente di esplorare, acquistare e provisioning dei dispositivi certificati per Microsoft Teams.  

 Per usare lo store dei dispositivi nell'interfaccia di amministrazione di Teams, passare a **Dispositivi > Store**.

## <a name="requirements"></a>Requisiti

Per usare l'archivio dispositivi, è necessario essere un amministratore globale o un amministratore di Teams.

## <a name="browse-the-store"></a>Esplora lo Store

Lo store dei dispositivi include tutti i dispositivi certificati per Teams, inclusi auricolari, fotocamere Web e dispositivi Teams come Teams Rooms, telefoni da tavolo e schermi di Teams. È possibile ordinare, filtrare o eseguire ricerche per trovare il dispositivo necessario all'organizzazione.

## <a name="purchase-devices"></a>Acquista dispositivi

Quando si acquistano dispositivi dallo store del dispositivo, il pagamento e l'evasione dei pagamenti, inclusa la spedizione e la consegna, vengono gestiti da UnifiedCommunications.com, un partner di evasione dei dati di terze parti Microsoft.  

Puoi pagare con una carta di credito o un ordine d'acquisto. Il pagamento dell'ordine di acquisto richiede la configurazione una tantum con il provider di evasione ordini.

Tutti gli ordini possono essere restituiti fino a 30 giorni dopo la consegna.

## <a name="data-handling-and-sharing"></a>Gestione e condivisione dei dati

L'archivio dispositivi di Teams deve condividere le informazioni di base su utenti e società, inclusi i GUID di utenti e tenant, con UnifiedCommunications.com per consentire l'acquisto nell'interfaccia di amministrazione di Teams.

La condivisione dei dati è disattivata per impostazione predefinita. Per abilitarla, passare allo store dei dispositivi di Teams, selezionare l'icona delle impostazioni e attivare l'impostazione.  

Quando questa impostazione è disattivata, i dati non verranno condivisi e potrai esplorare lo store dei dispositivi di Teams, ma non potrai effettuare acquisti. I dati raccolti e condivisi con il provider di evasione dei dati mentre l'impostazione era attivata vengono elaborati come specificato nella loro informativa sulla privacy.

## <a name="order-tracking-and-history"></a>Monitoraggio e cronologia degli ordini

Puoi visualizzare la cronologia degli ordini in **Store > Cronologia ordini**, che include tutti gli ordini effettuati da te e da altri amministratori dell'organizzazione. La cronologia ordini include anche lo stato della spedizione dei tuoi ordini. Per domande su verifica dell'ordine, resi o rimborsi, contatta UnifiedCommunications.com. Le informazioni di contatto sono disponibili nella pagina Cronologia ordini.

Gli ordini effettuati nell'archivio dispositivi di Teams e tutti i dati associati vengono classificati come ordini tenant e dati del tenant.

## <a name="provision-devices"></a>Effettuare il provisioning dei dispositivi

Quando si acquistano dispositivi che supportano il provisioning remoto, l'indirizzo MAC di tali dispositivi viene aggiunto automaticamente all'interfaccia di amministrazione di Teams quando il dispositivo viene spedito. A seconda dell'ordine e della data di spedizione, possono essere necessari circa 5 giorni prima che l'indirizzo MAC venga visualizzato nell'interfaccia di amministrazione di Teams.

Una volta forniti i dispositivi, vedi [Effettuare il provisioning remoto dei dispositivi](remote-provision-remote-login.md#generate-a-verification-code) per completare il processo di provisioning e accesso.
