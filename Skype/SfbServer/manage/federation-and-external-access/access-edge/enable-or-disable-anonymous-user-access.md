---
title: Abilitare o disabilitare l'accesso utente anonimo
ms.reviewer: null
'ms:assetid': f10c19e6-b6f9-4d26-9923-0165f36e4af8
'ms:mtpsurl': 'https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)'
'ms:contentKeyID': 49733872
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: Come abilitare e disabilitare l'accesso utente anonimo in Skype for Business Server.
---

# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Abilitare o disabilitare l'accesso utente anonimo in Skype for Business Server

Gli utenti anonimi sono utenti che non dispongono di un account utente in Servizi di dominio Active Directory dell'organizzazione o in un dominio federato supportato, ma possono essere invitati a partecipare in remoto a una conferenza locale. Consentendo la partecipazione anonima alle riunioni, si consente agli utenti anonimi, ovvero agli utenti la cui identità viene verificata solo mediante la chiave riunione o conferenza, di partecipare alle riunioni. A tale scopo, è necessario abilitare la partecipazione anonima per la propria organizzazione.

Se successivamente si desidera impedire temporaneamente o definitivamente l'accesso da parte di utenti anonimi, è possibile disabilitarlo per l'organizzazione. Eseguire la procedura illustrata in questa sezione per abilitare o disabilitare l'accesso utente anonimo per la propria organizzazione.

> [!NOTE]  
> Abilitando l'accesso utente anonimo per l'organizzazione, si specifica solo che i server che eseguono il servizio Access Edge supportano l'accesso da parte di utenti anonimi. Tali utenti non possono partecipare alle riunioni dell'organizzazione finché non viene configurato e applicato almeno un criterio di conferenza a uno o più utenti o gruppi di utenti. Gli unici utenti che possono invitare utenti anonimi alle riunioni sono quelli a cui è stato assegnato il criterio di conferenza configurato per supportare l'invito di utenti anonimi. Per informazioni dettagliate sulla configurazione dei criteri di conferenza per supportare l'invito di utenti anonimi, vedere [Manage conferencing policies](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Per abilitare o disabilitare l'accesso utente anonimo per l'organizzazione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Configurazione Access Edge**.

4.  Nella pagina **Configurazione Access Edge** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica configurazione Access Edge** eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso utente anonimo per l'organizzazione, selezionare la casella di controllo **Abilita comunicazioni con utenti anonimi**.
    
      - Per disabilitare l'accesso utente anonimo per l'organizzazione, deselezionare la casella di controllo **Abilita comunicazioni con utenti anonimi**.

6.  Fare clic su **Commit**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'accesso utente anonimo tramite Windows PowerShell cmdlet

È possibile gestire l'accesso utente anonimo utilizzando Windows PowerShell e il cmdlet **Set-CsAccessEdgeConfiguration**. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Per abilitare l'accesso utente anonimo

  - Per abilitare l'accesso utente anonimo, impostare il valore della proprietà **AllowAnonymousUsers** su True ($True):<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Per disabilitare l'accesso utente anonimo

  - Per disabilitare l'accesso utente anonimo, impostare il valore della proprietà **AllowAnonymousUsers** su False ($False):<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Vedere anche

[Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy)  
