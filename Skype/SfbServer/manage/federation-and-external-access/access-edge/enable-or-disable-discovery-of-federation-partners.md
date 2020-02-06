---
title: Abilitare o disabilitare l'individuazione dei partner della federazione
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Al momento della distribuzione degli Edge Server e della federazione abilitata per l'organizzazione, è necessario specificare se supportare l'individuazione automatica dei domini partner federati.
ms.openlocfilehash: a64e2056feacbee076fcaf9b0012a36f72c91523
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818397"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Abilitare o disabilitare l'individuazione dei partner federativi in Skype for Business Server

Al momento della distribuzione degli Edge Server e della federazione abilitata per l'organizzazione, è necessario specificare se supportare l'individuazione automatica dei domini partner federati. Usare la procedura descritta in questo argomento per modificare la configurazione.

> [!NOTE]  
> La procedura seguente presuppone che tu abbia già abilitato la Federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della Federazione, vedere [abilitare o disabilitare l'accesso remoto agli utenti](enable-or-disable-remote-user-access.md).

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Per abilitare o disabilitare l'individuazione automatica dei domini federati per l'organizzazione

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**, fare clic su **configurazione bordo di Access**.

4.  Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica configurazione di Access Edge**, in **abilitare le comunicazioni con gli utenti federati**, selezionare o deselezionare la casella di controllo **Abilita individuazione dominio partner** per abilitare o disabilitare l'individuazione automatica dei domini partner.

6.  Fare clic su **Commit**.

Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Skype for Business Server, è necessario che siano configurati almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati. Per informazioni dettagliate, vedere [abilitare o disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione](enable-or-disable-federation-and-public-im-connectivity.md). Per informazioni dettagliate su come controllare l'accesso per specifici domini federati, vedere [gestire i domini federati SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) e [gestire i provider federati SIP](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'individuazione dei partner federativi tramite i cmdlet di Windows PowerShell

L'individuazione dei partner federativi può essere gestita tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Per abilitare l'individuazione dei partner federativi

  - Per abilitare l'individuazione dei partner federativi, imposta il valore della proprietà **EnablePartnerDiscovery** su True ($true). Tieni presente che devi abilitare il routing SRV DNS per cambiare il valore della proprietà.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Per disabilitare l'individuazione dei partner federativi

  - Per disabilitare l'individuazione dei partner federativi, imposta il valore della proprietà **EnablePartnerDiscovery** su False ($false):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

