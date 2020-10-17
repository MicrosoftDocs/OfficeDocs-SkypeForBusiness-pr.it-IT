---
title: 'Lync Server 2013: aggiungere un Survivable Branch Appliance ad Active Directory'
description: 'Lync Server 2013: aggiungere un Survivable Branch Appliance ad Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd06332679be0819cf3002f344a62a7ce1d5a9f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567892"
---
# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Aggiungere un Survivable Branch Appliance ad Active Directory in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-23_

Se si prevede di distribuire un Survivable Branch Appliance, è necessario aggiungere il Survivable Branch Appliance ai servizi di dominio Active Directory. Eseguire questa procedura nel sito centrale.

<div>


> [!IMPORTANT]  
> Eseguire questa procedura solo se si sta distribuendo un Survivable Branch Appliance. Non eseguirlo se si sta distribuendo un Survivable Branch Server.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>Per aggiungere un Survivable Branch Appliance a Servizi di dominio Active Directory

1.  Eseguire l'accesso a un server membro come membro del gruppo Enterprise Admins.

2.  Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **Utenti e computer di Active Directory**.

3.  Scegliere **Nuovo** dal menu **Azioni** e quindi fare clic su **Computer**.

4.  Nella finestra di dialogo **nuovo oggetto-computer** Digitare un nome per l'oggetto computer Survivable Branch Appliance (ad esempio, BranchOffice1), quindi fare clic su **Cambia**.

5.  Nella finestra di dialogo **Seleziona utente o gruppo** aggiungere il gruppo RTCUniversalSBATechnicians e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Un membro del gruppo RTCUniversalSBATechnicians nel sito di succursale aggiungerà successivamente questo dispositivo al dominio.

    
    </div>

6.  Fare clic su **OK** per salvare l'oggetto computer Survivable Branch Appliance.

7.  Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **ADSI Edit**.

8.  In **ADSI Edit** fare clic con il pulsante destro del mouse sull'oggetto computer creato nei passaggi precedenti e quindi scegliere **Properties**.

9.  Nell'elenco degli attributi fare clic su **servicePrincipalName** e quindi su **Edit**.

10. Nel campo **valore da aggiungere** digitare host/ \<SBA FQDN\> dove \<SBA FQDN\> è il nome di dominio completo (FQDN) del Survivable Branch Appliance. Digitare ad esempio **HOST/BranchOffice1.contoso.com**.

11. Fare clic su **OK** per salvare l'impostazione dell'attributo **servicePrincipalName** e quindi su **OK** per salvare le proprietà dell'oggetto computer.

12. In **Utenti e computer di Active Directory** fare clic con il pulsante destro del mouse su **Utenti**, scegliere **Nuovo** e quindi fare clic su **Utente**.

13. Immettere le informazioni nella procedura guidata per creare un account utente di dominio per un Survivable Branch Appliance tecnico.

14. In **Utenti e computer di Active Directory** fare clic su **Utenti**, fare clic con il pulsante destro del mouse sull'oggetto utente e quindi scegliere **Aggiungi a un gruppo**.

15. In **Immettere i nomi degli oggetti da selezionare** digitare **RTCUniversalSBATechnicians** e quindi fare clic su **OK**.

16. Ripetere i passaggi 12-15 per ogni tecnico del sito di succursale.

**Passaggio successivo**: [aggiungere siti di succursale alla topologia in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

