---
title: 'Lync Server 2013: delega del controllo amministrativo di Lync Server'
description: 'Lync Server 2013: delega del controllo amministrativo di Lync Server.'
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
ms.openlocfilehash: a8d3710af2d194a5aa4ebdd7291be2ee58176507
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567492"
---
# <a name="delegating-administrative-control-of-lync-server-2013"></a>Delega del controllo amministrativo di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

In Lync Server 2013, le attività amministrative vengono delegate agli utenti utilizzando la nuova funzionalità di controllo di accesso basato sui ruoli (RBAC). Quando si installa Lync Server, viene creato un certo numero di ruoli RBAC. Questi ruoli corrispondono ai gruppi di protezione universali in servizi di dominio Active Directory. Ad esempio, il ruolo RBAC CsHelpDesk corrisponde al gruppo CsHelpDesk trovato nel contenitore utenti in servizi di dominio Active Directory. Inoltre, ciascun ruolo RBAC è associato a un set di cmdlet di Windows PowerShell di Lync Server. Questi cmdlet rappresentano le attività che possono essere eseguite dagli utenti a cui è stato assegnato il ruolo RBAC specificato. Ad esempio, al ruolo CsHelpDesk sono stati assegnati i cmdlet Lock-CsClientPin e UnlockCsClientPin. Questo significa che gli utenti a cui è stato assegnato il ruolo CsHelpDesk possono bloccare e sbloccare i numeri PIN dell'utente. Tuttavia, al ruolo CsHelpDesk non è stato assegnato il cmdlet New-CsVoicePolicy. Ciò significa che gli utenti a cui è stato assegnato il ruolo CsHelpDesk non possono creare nuovi criteri vocali.

<div>

## <a name="viewing-information-about-rbac-roles"></a>Visualizzazione delle informazioni sui ruoli RBAC

È possibile recuperare le informazioni di base sui ruoli RBAC eseguendo il comando riportato di seguito dall'interno di Lync Server Management Shell:

    Get-CsAdminRole

Tenere presente che l'identità del ruolo RBAC (ad esempio, CsVoiceAdministrator) ha un mapping diretto a un gruppo di sicurezza trovato nel contenitore utenti in servizi di dominio Active Directory.

Per visualizzare un elenco dei cmdlet assegnati a un ruolo, utilizzare un comando simile al seguente:

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>Assegnazione di un ruolo RBAC a un utente

Per assegnare un ruolo RBAC a un utente, è necessario aggiungere quell'utente al gruppo di sicurezza di Active Directory appropriato. Ad esempio, per assegnare il ruolo CsLocationAdministrator a un utente, è necessario aggiungere tale utente al gruppo CsLocationAdministrator. A tale scopo, è possibile eseguire la procedura seguente.

**Per assegnare un utente a un gruppo di sicurezza**

1.  Utilizzando un account che dispone dell'autorizzazione per modificare i membri di un gruppo di Active Directory, eseguire l'accesso a un computer in cui è stato installato Utenti e computer di Active Directory.

2.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Utenti e computer di Active Directory**.

3.  In Utenti e computer di Active Directory espandere il nome del dominio e fare clic sul contenitore degli** **utenti.

4.  Fare clic con il pulsante destro del mouse sul gruppo di sicurezza **CsLocationAdministrator** e scegliere **Proprietà**.

5.  Nella finestra di dialogo **Proprietà** fare clic su **Aggiungi** nella scheda **Membri**.

6.  Nella finestra di dialogo **Seleziona utenti, computer o gruppi** digitare il nome utente o il nome visualizzato dell'utente da aggiungere al gruppo, ad esempio **Ken Myer**, nella casella **Immettere i nomi degli oggetti da selezionare** e quindi fare clic su **OK**.

7.  Nella finestra di dialogo **Proprietà** fare clic su **OK**.

Per verificare che il ruolo RBAC sia stato assegnato, utilizzare il cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) passandogli il nome di account SAM (SamAccountName), ovvero il nome di accesso di Active Directory, dell'utente. Ad esempio, eseguire questo comando dall'interno di Lync Server Management Shell:

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

