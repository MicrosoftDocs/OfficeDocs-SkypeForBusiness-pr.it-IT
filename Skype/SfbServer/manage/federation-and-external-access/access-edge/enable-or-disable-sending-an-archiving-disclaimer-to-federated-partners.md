---
title: Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione ai partner federati
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188861"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione a partner federati in Skype for Business Server

Al momento della distribuzione degli Edge Server e della federazione abilitata per l'organizzazione, è necessario specificare se inviare automaticamente la dichiarazione di non responsabilità per l'archiviazione a partner federati. Se si archiviano comunicazioni esterne, è necessario abilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione. Usare la procedura descritta in questo argomento per modificare la configurazione.

> [!NOTE]
> La procedura seguente presuppone che tu abbia già abilitato la Federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della Federazione, vedere [abilitare o disabilitare l'accesso remoto agli utenti](enable-or-disable-remote-user-access.md).


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Per abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione a partner federati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**, fare clic su **configurazione bordo di Access**.

4.  Nella scheda **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica configurazione di Access Edge**, in **abilitare le comunicazioni con gli utenti federati**, selezionare o deselezionare la casella di controllo **Invia Disclaimer per l'archiviazione ai partner federati** per abilitare o disabilitare l'invio automatico dell'archiviazione Disclaimer.

6.  Fare clic su **Commit**.

Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Skype for Business Server, è necessario che siano configurati almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati. Per informazioni dettagliate su come controllare l'accesso per specifici domini federati, vedere [configurare il supporto per i domini esterni](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)consentiti.


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione della dichiarazione di non responsabilità per l'archiviazione tramite i cmdlet di Windows PowerShell

L'uso della dichiarazione di non responsabilità per l'archiviazione può essere gestito tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Per abilitare la dichiarazione di non responsabilità per l'archiviazione

  - Per abilitare la dichiarazione di non responsabilità per l'archiviazione, imposta il valore della proprietà **EnableArchivingDisclaimer** su True ($true):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Per disabilitare la dichiarazione di non responsabilità per l'archiviazione

  - Per disabilitare la dichiarazione di non responsabilità per l'archiviazione, imposta il valore della proprietà **EnableArchivingDisclaimer** su False ($false):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


