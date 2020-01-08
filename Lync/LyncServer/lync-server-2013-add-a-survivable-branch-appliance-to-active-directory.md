---
title: 'Lync Server 2013: Aggiungere un Survivable Branch Appliance ad Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc057318a0d241a28b8529802ea9f2016a1f5b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Aggiungere un Survivable Branch Appliance ad Active Directory in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-23_

Se si prevede di distribuire un Survivable Branch Appliance, è necessario aggiungere il Survivable Branch Appliance a servizi di dominio Active Directory. Eseguire questa procedura nel sito centrale.

<div>


> [!IMPORTANT]  
> Eseguire questa procedura solo se si sta distribuendo un Survivable Branch Appliance. Non eseguire questa operazione se si sta distribuendo un Survivable Branch Server.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>Per aggiungere un Survivable Branch Appliance a servizi di dominio Active Directory

1.  Accedere a un server membro come membro del gruppo amministratori aziendali.

2.  Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **utenti e computer di Active Directory**.

3.  Nel menu **azioni** fare clic su **nuovo** e quindi su **computer**.

4.  Nella finestra di dialogo **nuovo oggetto-computer** Digitare un nome per l'oggetto computer Survivable Branch Appliance, ad esempio BranchOffice1, e quindi fare clic su **Cambia**.

5.  Nella finestra di dialogo **Seleziona utente o gruppo** aggiungere il gruppo RTCUniversalSBATechnicians e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Un membro del gruppo RTCUniversalSBATechnicians nel sito della filiale aggiungerà questo dispositivo al dominio in un secondo momento.

    
    </div>

6.  Fare clic su **OK** per salvare l'oggetto computer Survivable Branch Appliance.

7.  Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Modifica ADSI**.

8.  In **Modifica ADSI**fare clic con il pulsante destro del mouse sull'oggetto computer creato nei passaggi precedenti e quindi scegliere **Proprietà**.

9.  Nell'elenco attributo fare clic su **servicePrincipalName**e quindi su **modifica**.

10. Nel campo **valore da aggiungere** \<digitare FQDN\> host/SBA in cui \<l'FQDN di\> SBA è il nome di dominio completo (FQDN) dell'appliance Survivable Branch. Ad esempio, digita **host/BranchOffice1. contoso. com**.

11. Fare clic su **OK** per salvare l'impostazione dell'attributo **servicePrincipalName** e quindi fare clic su **OK** per salvare le proprietà dell'oggetto computer.

12. In **utenti e computer di Active Directory**fare clic con il pulsante destro del mouse su **utenti**, scegliere **nuovo**e quindi fare clic su **utente**.

13. Immettere le informazioni nella procedura guidata per creare un account utente di dominio per un tecnico Survivable Branch Appliance.

14. In **utenti e computer di Active Directory**fare clic su **utenti**, fare clic con il pulsante destro del mouse sull'oggetto utente e quindi scegliere **Aggiungi a un gruppo**.

15. In **immettere i nomi degli oggetti da selezionare**digitare **RTCUniversalSBATechnicians**e quindi fare clic su **OK**.

16. Ripetere i passaggi 12-15 per ogni tecnico del sito filiale.

**Passaggio successivo**: [aggiungere siti di succursale alla topologia in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

