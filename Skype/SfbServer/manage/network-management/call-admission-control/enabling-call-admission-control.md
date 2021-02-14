---
title: Abilitazione del controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " Dopo aver configurato la rete del servizio Controllo di ammissione di chiamata, è necessario abilitare il servizio Controllo di ammissione di chiamata per applicare le limitazioni della larghezza di banda."
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816506"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Abilitazione del controllo di ammissione di chiamata in Skype for Business Server

Il servizio Controllo di ammissione di chiamata è una rete di aree, siti e subnet che consentono di applicare restrizioni relative alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo avere configurato tale rete, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda. A tale scopo, è possibile utilizzare il Pannello di controllo di Skype for Business Server.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Per abilitare il controllo di ammissione di chiamata dal Pannello di controllo di Skype for Business Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Globale.**

4.  Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**.
   
    > [!NOTE]  
    > È possibile configurare una sola rete per qualsiasi distribuzione di Skype for Business Server, quindi non ci sarà mai più di una configurazione di rete nell'elenco. Non è possibile rinominare la configurazione globale.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Nella pagina **Modifica Impostazioni globali** selezionare la casella di controllo **Abilita il controllo di ammissione di chiamata** e quindi fare clic su **Commit**.

Quando si fa clic su **Commit**, si esegue un test della configurazione. La finestra di dialogo **Modifica Impostazioni globali** si chiude e si torna alla pagina **Globale**. Si riceverà un avviso se nella configurazione di rete vengono rilevati eventuali errori o incongruenze che ne impediscono il corretto funzionamento, ad esempio se non tutte le aree sono connesse a tutte le altre aree mediante una route tra aree.

Se si apportano modifiche alla configurazione di rete, sarà possibile eseguire di nuovo la convalida aprendo la configurazione globale e facendo clic su **Commit**. Non è necessario disabilitare prima il controllo di ammissione di chiamata, perciò lasciare selezionata la casella di controllo e fare clic su **Commit**. È possibile procedere in questo modo in qualsiasi momento senza apportare modifiche alla configurazione.

## <a name="see-also"></a>Vedere anche

[Pianificare il controllo di ammissione di chiamata](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Distribuire il controllo di ammissione di chiamata](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
