---
title: 'Lync Server 2013: Assegnare i criteri di conferenza per supportare gli utenti anonimi'
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
ms.openlocfilehash: bab1c3da15bd72bb03233ca05d86e355eebbb233
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Assegnare i criteri di conferenza per supportare gli utenti anonimi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Per impostazione predefinita, a tutti gli utenti viene impedito di invitare utenti anonimi a partecipare a una riunione. Puoi controllare chi può invitare utenti anonimi configurando un criterio di conferenza per supportare utenti anonimi e applicando i criteri di conferenza a utenti specifici. Per informazioni dettagliate su come configurare i criteri di conferenza per il supporto degli utenti anonimi, vedere [creare o modificare criteri di conferenza in Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) e [gestire la Federazione e l'accesso esterno a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Usare la procedura descritta in questa sezione per applicare un criterio di conferenza già creato a uno o più utenti o gruppi di utente.

<div>


> [!NOTE]  
> Oltre a configurare e applicare un criterio per consentire agli utenti di invitare utenti anonimi, è anche necessario abilitare il supporto per gli utenti anonimi per l'organizzazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">configurare i criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Per configurare un criterio utente per la partecipazione anonima alle riunioni

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi eseguire una delle operazioni seguenti:
    
    1.  Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**. Creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnableAnonymous** per un criterio utente che consente la comunicazione con utenti anonimi.
    
    2.  Per configurare un criterio utente esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

4.  Nella finestra di dialogo **criteri di conferenza** selezionare la casella **di controllo Consenti ai partecipanti di invitare utenti anonimi** .

5.  Fare clic su **Commit**.

6.  Nella barra di spostamento sinistra fare clic su **utenti**, cercare nell'account utente che si desidera configurare.

7.  Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.

8.  In **modifica utenti di Lync Server** in **criteri di conferenza**Selezionare il criterio utente con la configurazione di accesso utente anonima che si vuole applicare a questo utente.
    
    <div>
    

    > [!NOTE]  
    > Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni di installazione predefinite del server e vengono applicate automaticamente dal server.

    
    </div>

Per consentire agli utenti di invitare utenti anonimi alle conferenze, è anche necessario abilitare il supporto per gli utenti anonimi dell'organizzazione. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.

</div>

</div>

<span> </span>

</div>

</div>

</div>

