---
title: Abilitare o disabilitare l'accesso degli utenti anonimi
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a368a364f39fe8178e9ce4f17a17bea96fea7b23
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188894"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Abilitare o disabilitare l'accesso anonimo agli utenti in Skype for Business Server

Gli utenti anonimi sono utenti che non dispongono di un account utente nei servizi di dominio Active Directory dell'organizzazione o in un dominio federato supportato, ma possono essere invitati a partecipare in remoto in una conferenza locale. Consentendo la partecipazione anonima alle riunioni, è possibile abilitare gli utenti anonimi, ovvero gli utenti la cui identità viene verificata solo tramite la riunione o la chiave di conferenza, per partecipare alle riunioni. Per consentire la partecipazione anonima, è necessario abilitarla per l'organizzazione.

Se in seguito si vuole impedire temporaneamente o definitivamente l'accesso da parte di utenti anonimi, è possibile disabilitarlo per l'organizzazione. Usare la procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti anonimi per l'organizzazione.

> [!NOTE]  
> Abilitando l'accesso degli utenti anonimi per l'organizzazione, devi solo specificare che i server che esegue il servizio Access Edge supportano l'accesso da parte di utenti anonimi. Gli utenti anonimi non possono partecipare a riunioni dell'organizzazione fino a quando non vengono configurati almeno un criterio di conferenza e lo si applicano a uno o più utenti o gruppi di utente. Gli unici utenti che possono invitare utenti anonimi alle riunioni sono gli utenti a cui sono assegnati i criteri di conferenza configurati per il supporto degli utenti anonimi. Per informazioni dettagliate sulla configurazione dei criteri di conferenza per supportare l'invito agli utenti anonimi, vedere [gestire i criteri di conferenza](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Per abilitare o disabilitare l'accesso degli utenti anonimi per l'organizzazione

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **configurazione bordo di Access**.

4.  Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica configurazione di Access Edge**eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti anonimi per l'organizzazione, selezionare la casella di controllo **Abilita comunicazioni con utenti anonimi** .
    
      - Per disabilitare l'accesso degli utenti anonimi per l'organizzazione, deselezionare la casella di controllo **Abilita comunicazioni con utenti anonimi** .

6.  Fare clic su **Commit**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'accesso degli utenti anonimi tramite i cmdlet di Windows PowerShell

Per gestire l'accesso degli utenti anonimi, è possibile usare Windows PowerShell e il cmdlet **Set-CsAccessEdgeConfiguration** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Per abilitare l'accesso degli utenti anonimi

  - Per abilitare l'accesso degli utenti anonimi, imposta il valore della proprietà **AllowAnonymousUsers** su True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Per disabilitare l'accesso degli utenti anonimi

  - Per disabilitare l'accesso anonimo agli utenti, imposta il valore della proprietà **AllowAnonymousUsers** su False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Vedere anche

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
