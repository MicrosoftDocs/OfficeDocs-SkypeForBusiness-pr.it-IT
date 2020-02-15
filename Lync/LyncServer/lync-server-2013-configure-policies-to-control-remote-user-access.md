---
title: "Lync Server 2013: configurare i criteri per il controllo dell'accesso degli utenti remoti"
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
ms.openlocfilehash: ccef43d31b6fecf0d55c31f0b6df958dc67b7e7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Configurazione di criteri per il controllo dell'accesso degli utenti remoti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

È possibile configurare uno o più criteri di accesso utente esterno per controllare se gli utenti remoti possono collaborare con gli utenti interni di Lync Server. Per controllare l'accesso degli utenti remoti è possibile configurare criteri a livello globale, di sito e di utente. I criteri a livello di sito hanno la priorità sui criteri globali e i criteri utente hanno la priorità sui criteri a livello di sito e globali. Per informazioni dettagliate sui tipi di criteri che è possibile configurare, vedere [Managing Federation and External Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md). Le impostazioni criteri di Lync Server applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.

<div>


> [!NOTE]  
> È possibile configurare criteri per il controllo dell'accesso degli utenti remoti anche se non si è abilitato l'accesso utente remoto per l'organizzazione. I criteri configurati, tuttavia, verranno applicati solo dopo l'abilitazione dell'accesso utente remoto per l'organizzazione. Per informazioni dettagliate sull'abilitazione dell'accesso degli utenti remoti, vedere <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</A>. Inoltre, se si specifica un criterio utente per il controllo dell'accesso degli utenti remoti, il criterio si applica solo agli utenti abilitati per Lync Server e configurati per l'utilizzo dei criteri. Per informazioni dettagliate su come specificare gli utenti che possono accedere a Lync Server da postazioni remote, vedere <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync server 2013</A>.



</div>

Eseguire la procedura seguente per configurare ogni criterio di accesso esterno che si desidera utilizzare per controllare l'accesso degli utenti remoti.

<div>


> [!NOTE]  
> Questa procedura descrive come configurare un criterio solo per abilitare le comunicazioni con gli utenti remoti, ma qualsiasi criterio configurato per il supporto dell'accesso utente remoto può configurare anche l'accesso degli utenti federati e l'accesso degli utenti pubblici. Per informazioni dettagliate sulla configurazione dei criteri per il supporto degli utenti federati, vedere <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to Control Federated User Access in Lync Server 2013</A>. Per informazioni dettagliate sulla configurazione dei criteri per il supporto degli utenti pubblici, vedere <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">creare o modificare provider federati SIP pubblici in Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Per configurare un criterio di accesso esterno per il supporto dell'accesso utente remoto

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella pagina **Criteri di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Per configurare il criterio globale per il supporto dell'accesso utente remoto, fare clic sul criterio globale, su **Modifica** e quindi su **Mostra dettagli**.
    
      - Per creare nuovi criteri di sito, fare clic su **Nuovo** e quindi su **Criteri sito**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.
    
      - Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. In **Nuovi criteri di accesso esterno** creare un nome univoco nel campo **Nome** che indichi lo scopo del criterio, ad esempio **AbilitaUtentiRemoti** per un criterio utente che abilita le comunicazioni per gli utenti remoti.
    
      - Per modificare criteri esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

5.  (Facoltativo) Se si desidera aggiungere o modificare una descrizione, specificare le informazioni per i criteri in **Descrizione**.

6.  Eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso utente remoto per il criterio, selezionare la casella di controllo **Abilita comunicazioni con utenti remoti**.
    
      - Per disabilitare l'accesso utente remoto per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con utenti remoti**.

7.  Fare clic su **Commit**.

Per abilitare l'accesso utente remoto è necessario abilitare anche il supporto dell'accesso utente remoto nell'organizzazione. Per ulteriori informazioni, vedere [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.

Se si tratta di un criterio utente è inoltre necessario applicare il criterio agli utenti ai quali si desidera consentire di effettuare l'accesso in remoto. Per ulteriori informazioni, vedere [assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.

</div>

</div>

<span> </span>

</div>

</div>

</div>

