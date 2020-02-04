---
title: "Lync Server 2013: Configurare criteri per controllare l'accesso degli utenti remoti"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8542e7d64198cb83df58885b9240e07066288d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Configurare criteri per controllare l'accesso degli utenti remoti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

Si configurano uno o più criteri di accesso degli utenti esterni per controllare se gli utenti remoti possono collaborare con gli utenti interni di Lync Server. Per controllare l'accesso degli utenti remoti, è possibile configurare i criteri a livello globale, sito e utente. I criteri del sito sostituiscono i criteri globali e i criteri utente sostituiscono il sito e i criteri globali. Per informazioni dettagliate sui tipi di criteri che è possibile configurare, vedere [gestione della Federazione e accesso esterno a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md). Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.

<div>


> [!NOTE]  
> È possibile configurare i criteri per controllare l'accesso degli utenti remoti, anche se non è stato abilitato l'accesso degli utenti remoti per l'organizzazione. Tuttavia, i criteri configurati sono attivi solo quando si ha accesso a utenti remoti abilitato per l'organizzazione. Per informazioni dettagliate sull'abilitazione dell'accesso degli utenti remoti, vedere <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">abilitare o disabilitare la connettività di messaggistica istantanea pubblica e della Federazione in Lync Server 2013</A>. Inoltre, se specifichi un criterio utente per controllare l'accesso degli utenti remoti, il criterio si applica solo agli utenti abilitati per Lync Server e configurati per l'uso dei criteri. Per informazioni dettagliate su come specificare gli utenti che possono accedere a Lync Server da percorsi remoti, vedere <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">assegnare criteri di accesso degli utenti esterni a un utente abilitato a Lync in Lync server 2013</A>.



</div>

Usare la procedura seguente per configurare ogni criterio di accesso esterno che si vuole usare per controllare l'accesso degli utenti remoti.

<div>


> [!NOTE]  
> Questa procedura descrive come configurare un criterio solo per abilitare le comunicazioni con gli utenti remoti, ma ogni criterio configurato per supportare l'accesso degli utenti remoti può anche configurare l'accesso degli utenti federati e l'accesso degli utenti pubblici. Per informazioni dettagliate sulla configurazione dei criteri per il supporto degli utenti federati, vedere <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configurare i criteri per controllare l'accesso degli utenti federati in Lync Server 2013</A>. Per informazioni dettagliate sulla configurazione dei criteri per il supporto degli utenti pubblici, vedere <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">creare o modificare provider federati SIP pubblici in Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Per configurare un criterio di accesso esterno per supportare l'accesso degli utenti remoti

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **criteri di accesso esterno**.

4.  Nella pagina **criteri di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Per configurare i criteri globali per il supporto dell'accesso degli utenti remoti, fare clic sul criterio globale, scegliere **modifica**e quindi fare clic su **Mostra dettagli**.
    
      - Per creare un nuovo criterio sito, fare clic su **nuovo**e quindi su **criteri sito**. In **Seleziona un sito**fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.
    
      - Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**. In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnableRemoteUsers** , per un criterio utente che consente le comunicazioni per gli utenti remoti.
    
      - Per modificare un criterio esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Opzionale Se si vuole aggiungere o modificare una descrizione, specificare le informazioni per il criterio in **Descrizione**.

6.  Esegui una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti remoti per il criterio, selezionare la casella di controllo **Abilita comunicazioni con utenti remoti** .
    
      - Per disabilitare l'accesso degli utenti remoti per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con utenti remoti** .

7.  Fare clic su **Commit**.

Per abilitare l'accesso remoto agli utenti, è necessario abilitare anche il supporto per l'accesso degli utenti remoti nell'organizzazione. Per informazioni dettagliate, vedere [abilitare o disabilitare la connettività per la messaggistica istantanea e la Federazione in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.

Se si tratta di un criterio utente, è necessario applicare il criterio anche agli utenti che si vogliono connettere in remoto. Per informazioni dettagliate, vedere [assegnare criteri di accesso degli utenti esterni a un utente abilitato a Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.

</div>

</div>

<span> </span>

</div>

</div>

</div>

