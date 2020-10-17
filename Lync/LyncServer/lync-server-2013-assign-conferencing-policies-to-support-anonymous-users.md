---
title: 'Lync Server 2013: assegnare i criteri di conferenza per supportare gli utenti anonimi'
description: 'Lync Server 2013: assegnare i criteri di conferenza per supportare gli utenti anonimi.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e94c3097e3e21f854e91fdee1ad0b33c3b9f53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566162"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Assegnare i criteri di conferenza per supportare gli utenti anonimi in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Per impostazione predefinita, a tutti gli utenti è proibito invitare utenti anonimi a partecipare a una riunione. È possibile decidere chi può invitare utenti anonimi configurando un criterio di conferenza che li supporti e applicando tale criterio a utenti specifici. Per informazioni dettagliate su come configurare i criteri di conferenza per supportare gli utenti anonimi, vedere [Create or modify a Conferencing Policy in Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) e [Managing Federation and External Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Utilizzare la procedura in questa sezione per applicare criteri di conferenza già creati a uno o più utenti o gruppi di utenti.

<div>


> [!NOTE]  
> Oltre alla configurazione e all'applicazione di criteri per consentire agli utenti di invitare utenti anonimi, è inoltre necessario abilitare il supporto degli utenti anonimi per l'organizzazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to Control public User Access in Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Per configurare i criteri utente per la partecipazione anonima alle riunioni

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi eseguire una delle operazioni seguenti:
    
    1.  Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. Creare un nome univoco nel campo **Nome** che indichi lo scopo dei criteri, ad esempio **AbilitaAnonimi** per criteri utente per l'abilitazione delle comunicazioni per gli utenti anonimi.
    
    2.  Per configurare criteri utente esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

4.  Nella finestra di dialogo **Criteri conferenza** selezionare la casella di controllo **Consenti ai partecipanti di invitare utenti anonimi**.

5.  Fare clic su **Commit**.

6.  Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare.

7.  Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

8.  In **Modifica utente di Lync Server** in **Criteri conferenza** selezionare i criteri utente con la configurazione per l'accesso degli utenti anonimi che si desidera applicare all'utente.
    
    <div>
    

    > [!NOTE]  
    > Le impostazioni <STRONG> &lt; automatiche &gt; </STRONG> applicano le impostazioni di installazione predefinite del server e vengono applicate automaticamente dal server.

    
    </div>

Per consentire agli utenti di invitare utenti anonimi alle conferenze, è inoltre necessario abilitare il supporto per gli utenti anonimi nell'organizzazione. Per informazioni dettagliate, vedere [Configure policies to Control public User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.

</div>

</div>

<span> </span>

</div>

</div>

</div>

