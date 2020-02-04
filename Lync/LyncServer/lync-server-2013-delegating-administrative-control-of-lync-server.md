---
title: 'Lync Server 2013: Delega del controllo amministrativo di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 134d5a4abae1173cc1d74cecb876951cea6d72c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>Delega del controllo amministrativo di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

In Lync Server 2013 le attività amministrative vengono delegate agli utenti tramite la nuova funzionalità controllo di accesso basato sui ruoli. Quando si installa Lync Server, viene creato un numero di ruoli RBAC. Questi ruoli corrispondono ai gruppi di sicurezza universale in servizi di dominio Active Directory. Ad esempio, il ruolo RBAC CsHelpDesk corrisponde al gruppo CsHelpDesk trovato nel contenitore utenti in servizi di dominio Active Directory. Ogni ruolo RBAC è inoltre associato a un set di cmdlet di Windows PowerShell per Lync Server. Questi cmdlet rappresentano le attività che possono essere eseguite dagli utenti a cui è stato assegnato il ruolo RBAC specificato. Ad esempio, al ruolo CsHelpDesk sono stati assegnati i cmdlet Lock-CsClientPin e UnlockCsClientPin. Ciò significa che gli utenti a cui è stato assegnato il ruolo CsHelpDesk possono bloccare e sbloccare i numeri di PIN degli utenti. Tuttavia, al ruolo CsHelpDesk non è stato assegnato il cmdlet New-CsVoicePolicy. Ciò significa che gli utenti a cui è stato assegnato il ruolo CsHelpDesk non possono creare nuovi criteri vocali.

<div>

## <a name="viewing-information-about-rbac-roles"></a>Visualizzazione delle informazioni sui ruoli RBAC

È possibile recuperare le informazioni di base sui ruoli RBAC eseguendo il comando seguente all'interno di Lync Server Management Shell:

    Get-CsAdminRole

Tieni presente che l'identità del ruolo RBAC (ad esempio CsVoiceAdministrator) ha un mapping diretto a un gruppo di sicurezza trovato nel contenitore utenti in servizi di dominio Active Directory.

Per visualizzare un elenco dei cmdlet assegnati a un ruolo, usare un comando simile al seguente:

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>Assegnazione di un ruolo RBAC a un utente

Per assegnare un ruolo RBAC a un utente, è necessario aggiungere l'utente al gruppo di sicurezza Active Directory appropriato. Ad esempio, per assegnare il ruolo CsLocationAdministrator a un utente, è necessario aggiungere l'utente al gruppo CsLocationAdministrator. Questa operazione può essere eseguita eseguendo la procedura seguente:

**Per assegnare un utente a un gruppo di sicurezza**

1.  Utilizzando un account che disponga delle autorizzazioni per modificare l'appartenenza a un gruppo di Active Directory, accedere a un computer in cui sono stati installati utenti e computer di Active Directory.

2.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **utenti e computer di Active Directory**.

3.  In utenti e computer di Active Directory espandere il nome del dominio e fare clic sul contenitore **utenti** .

4.  Fare clic con il pulsante destro del mouse sul gruppo di sicurezza **CsLocationAdministrator**e quindi scegliere **Proprietà**.

5.  Nella scheda **membri** della finestra di dialogo **Proprietà** fare clic su **Aggiungi**.

6.  Nella finestra di dialogo **Seleziona utenti, computer, contatti o gruppi** Digitare il nome utente o il nome visualizzato dell'utente da aggiungere al gruppo, ad esempio **Ken**, nella casella **immettere i nomi degli oggetti da selezionare** e quindi fare clic su **OK**.

7.  Nella finestra di dialogo **Proprietà** fare clic su **OK**.

Per verificare che il ruolo RBAC sia stato assegnato, usare il cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) , passando il cmdlet sAMAccountName (nome accesso Active Directory) dell'utente. Ad esempio, Esegui questo comando dall'interno di Lync Server Management Shell:

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

