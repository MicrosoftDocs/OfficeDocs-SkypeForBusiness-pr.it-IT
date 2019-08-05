---
title: Abilitazione del controllo dell'ammissione alle chiamate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Dopo aver configurato la rete di controllo di ammissione chiamata (CAC), è necessario abilitare CAC per applicare le limitazioni della larghezza di banda."
ms.openlocfilehash: cbe3ad690f7061611a91474ce6df1fe39d84b0fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188588"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Abilitazione del controllo di ammissione alle chiamate in Skype for Business Server

Il servizio Controllo di ammissione di chiamata è una rete di aree, siti e subnet che consentono di applicare restrizioni alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo aver configurato la rete CAC, è necessario abilitare CAC per applicare le limitazioni della larghezza di banda. Per eseguire questa operazione, è possibile usare il pannello di controllo di Skype for Business Server.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Per abilitare CAC dal pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **globale**.

4.  Nella pagina **globale** fare clic sulla configurazione **globale** .
   
    > [!NOTE]  
    > Solo una rete può essere configurata per qualsiasi distribuzione di Skype for Business Server, quindi non ci saranno mai più configurazioni di rete nell'elenco. Non è possibile rinominare la configurazione globale.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **Modifica impostazioni globali** selezionare la casella di **controllo Abilita l'ammissione alle chiamate** e quindi fare clic su **conferma**.

Quando si fa clic su **commit**, si esegue un test della configurazione. La finestra di dialogo **Modifica impostazioni globali** viene chiusa, tornando alla pagina **globale** . Verrà visualizzato un messaggio di avviso in caso di errori o incongruenze individuati nella configurazione di rete che ne impediscono il corretto funzionamento, ad esempio se ogni area geografica non è connessa a tutte le altre aree geografiche tramite una route interregion.

Se si apportano modifiche alla configurazione di rete, è possibile eseguire di nuovo il controllo di convalida aprendo la configurazione globale e facendo clic su **commit**. Non è necessario disabilitare prima CAC: tenere selezionata la casella di controllo e fare clic su **conferma**. Puoi eseguire questa operazione in qualsiasi momento senza apportare modifiche alla configurazione.

## <a name="see-also"></a>Vedere anche

[Pianificazione del servizio Controllo di ammissione di chiamata](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Configurare il controllo di ammissione di chiamata](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
