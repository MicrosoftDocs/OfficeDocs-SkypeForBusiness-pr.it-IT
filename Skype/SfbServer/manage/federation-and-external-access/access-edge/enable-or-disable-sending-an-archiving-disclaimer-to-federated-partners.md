---
title: Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione ai partner federati
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 1f0238e177e74dc1263208f9a6a350158825d825
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817356"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione ai partner federati in Skype for Business Server

Al momento della distribuzione dei server perimetrali e dell'abilitazione della federazione per l'organizzazione, dovrebbe essere stato specificato se inviare automaticamente la dichiarazione di non responsabilità relativa all'archiviazione ai partner federati. Se si archiviano le comunicazioni esterne, è consigliabile abilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione. Utilizzare la procedura descritta in questo argomento per modificare tale configurazione.

> [!NOTE]
> Nella procedura che segue si presuppone che sia stata già abilitata la federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della federazione, vedere [Abilitare o disabilitare l'accesso degli utenti remoti.](enable-or-disable-remote-user-access.md)


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Per abilitare o disabilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione ai partner federati

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e su **Configurazione Access Edge**.

4.  Nella scheda **Configurazione Access Edge** fare clic su **Globale**, quindi su **Modifica** e infine su **Mostra dettagli**.

5.  In **Modifica configurazione Access Edge**, in **Abilita comunicazioni con utenti federati**, selezionare o deselezionare la casella di controllo **Invia dichiarazione di non responsabilità relativa all'archiviazione ai partner federati** per abilitare o disabilitare l'invio automatico della dichiarazione di non responsabilità relativa all'archiviazione.

6.  Fare clic su **Commit**.

Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Skype for Business Server, è inoltre necessario aver configurato almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati. Per informazioni dettagliate sul controllo dell'accesso per domini federati specifici, vedere [Configurare il supporto per i domini esterni consentiti.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione della dichiarazione di non responsabilità per l'archiviazione tramite Windows PowerShell cmdlet

L'utilizzo della dichiarazione di non responsabilità per l'archiviazione può essere gestito utilizzando Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration archiviazione. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Per abilitare la dichiarazione di non responsabilità per l'archiviazione

  - Per abilitare la dichiarazione di non responsabilità relativa all'archiviazione, impostare il valore della proprietà **EnableArchivingDisclaimer** su True ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Per disabilitare la dichiarazione di non responsabilità per l'archiviazione

  - Per disabilitare la dichiarazione di non responsabilità relativa all'archiviazione, impostare il valore della proprietà **EnableArchivingDisclaimer** su False ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


