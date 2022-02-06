---
title: Delegare il controllo amministrativo Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: ''
---

# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Delegare il controllo amministrativo Skype for Business Server 

In Skype for Business Server, le attività amministrative vengono delegate agli utenti tramite la funzionalità RBAC (Role-Based Access Control). Quando si installa Skype for Business Server, vengono creati automaticamente diversi ruoli RBAC. Questi ruoli corrispondono ai gruppi di sicurezza universali in Servizi di dominio Active Directory. Ad esempio, il ruolo RBAC CsHelpDesk corrisponde al gruppo CsHelpDesk presente nel contenitore Utenti in Servizi di dominio Active Directory. Inoltre, ogni ruolo RBAC è associato a un set di Skype for Business ServerWindows PowerShell cmdlet.   Questi cmdlet rappresentano le attività che possono essere eseguite dagli utenti a cui è stato assegnato il ruolo RBAC specificato. Ad esempio, al ruolo CsHelpDesk sono stati assegnati i cmdlet Lock-CsClientPin e UnlockCsClientPin. Ciò significa che gli utenti a cui è stato assegnato il ruolo CsHelpDesk possono bloccare e sbloccare i numeri PIN degli utenti. Tuttavia, al ruolo CsHelpDesk non è stato assegnato New-CsVoicePolicy cmdlet. Ciò significa che gli utenti a cui è stato assegnato il ruolo CsHelpDesk non possono creare nuovi criteri vocali.

## <a name="viewing-information-about-rbac-roles"></a>Visualizzazione delle informazioni sui ruoli RBAC

È possibile recuperare informazioni di base sui ruoli RBAC eseguendo il comando seguente da Skype for Business Server Management Shell:

`Get-CsAdminRole`

Tenere presente che l'identità del ruolo RBAC ,ad esempio CsVoiceAdministrator, dispone di un mapping diretto a un gruppo di sicurezza presente nel contenitore Utenti in Servizi di dominio Active Directory.

Per visualizzare un elenco dei cmdlet assegnati a un ruolo, utilizzare un comando simile al seguente:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Assegnazione di un ruolo RBAC a un utente

Per assegnare un ruolo RBAC a un utente, è necessario aggiungerlo al gruppo di sicurezza di Active Directory appropriato. Ad esempio, per assegnare il ruolo CsLocationAdministrator a un utente, è necessario aggiungere tale utente al gruppo CsLocationAdministrator. A tale scopo, è possibile eseguire la procedura seguente.

1. Utilizzando un account che dispone dell'autorizzazione per modificare i membri di un gruppo di Active Directory, eseguire l'accesso a un computer in cui è stato installato Utenti e computer di Active Directory.
2. Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Utenti e computer di Active Directory**.
3. In Utenti e computer di Active Directory espandere il nome del dominio e fare clic sul contenitore degli **** utenti.
4. Fare clic con il pulsante destro del mouse sul gruppo di sicurezza **CsLocationAdministrator** e scegliere **Proprietà**.
5. Nella finestra di dialogo **Proprietà** fare clic su **Aggiungi** nella scheda **Membri**.
6. Nella finestra di dialogo Seleziona utenti **, computer,** contatti o gruppi digitare il nome utente o il nome visualizzato dell'utente da aggiungere al gruppo, ad esempio Davide Garghente, nella casella Immettere i  nomi degli oggetti da selezionare e quindi fare clic su **OK**.
7. Nella finestra di dialogo **Proprietà** fare clic su **OK**.

Per verificare che il ruolo RBAC sia stato assegnato, utilizzare il cmdlet Get-CsAdminRoleAssignment passandogli il nome di account SAM (SamAccountName), ovvero il nome di accesso di Active Directory, dell'utente. Ad esempio, eseguire questo comando da Skype for Business Server Management Shell:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
