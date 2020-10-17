---
title: 'Lync Server 2013: configurare il supporto per i domini esterni consentiti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eaa9da579561464c46776662cacaca80dafe016
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517683"
---
# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Configurare il supporto per i domini esterni consentiti in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Se è stato configurato il supporto per i partner federati, è possibile specificare i domini che possono eseguire la federazione con l'organizzazione. Configurare uno o più domini esterni specifici come domini federati consentiti. A tale scopo, aggiungere ogni dominio all'elenco dei domini consentiti. Anche se per l'organizzazione è abilitata l'individuazione del partner, eseguire questa operazione se il dominio è un partner federato che potrebbe dover comunicare con oltre 1.000 utenti dell'organizzazione o inviare più di 20 messaggi al secondo. Se per l'organizzazione non è abilitata l'individuazione del partner, solo gli utenti dei domini esterni aggiunti all'elenco dei domini consentiti potranno partecipare alla messaggistica istantanea e alle conferenze con gli utenti dell'organizzazione. Se si desidera limitare l'accesso di un dominio federato a un server specifico che esegue il servizio Access Edge del partner federato, è possibile specificare il nome di dominio del server che esegue il servizio Access Edge per ogni dominio incluso nell'elenco dei domini consentiti.

<div>


> [!NOTE]  
> Questa procedura descrive come configurare il supporto per domini specifici, ma l'implementazione del supporto per gli utenti federati richiede inoltre di abilitare il supporto per gli utenti federati dell'organizzazione, nonché di configurare e applicare criteri per specificare quali utenti possono collaborare con gli utenti federati. Per informazioni dettagliate sull'abilitazione del supporto per gli utenti federati, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or Disable Remote User Access in Lync Server 2013</A>. Per informazioni dettagliate sulla configurazione dei criteri per il controllo della Federazione, vedere <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to Control Federated User Access in Lync Server 2013</A>.



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Per aggiungere un dominio esterno all'elenco dei domini consentiti

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Domini federati**.

4.  Nella pagina **Domini federati** fare clic su **Nuovo** e quindi su **Dominio consentito**.

5.  In **Nuovi domini federati** eseguire le operazioni seguenti:
    
      - In **Nome di dominio (o FQDN)** digitare il nome del dominio del partner federato.
        
        <div>
        

        > [!NOTE]  
        > Il nome deve essere univoco e non deve esistere già come dominio consentito per il server che esegue il servizio Access Edge. Il nome può essere costituito da un massimo di 256 caratteri.<BR>La ricerca in base al nome di dominio del partner federato si basa sulla corrispondenza del suffisso. Se ad esempio si digita <STRONG>contoso.com</STRONG>, la ricerca restituirà anche il dominio <STRONG>it.contoso.com</STRONG>.<BR>Un dominio di partner federato non può essere contemporaneamente bloccato e consentito. Lync Server 2013 impedisce l'avvenuto verificarsi in modo da non dover sincronizzare gli elenchi.

        
        </div>
    
      - Se si desidera limitare l'accesso per questo dominio federato agli utenti di un server specifico che esegue il servizio Access Edge, in **Servizio Access Edge (FQDN)** digitare l'FQDN del server del dominio federato che esegue il servizio Access Edge.
    
      - Se si desidera fornire ulteriori informazioni, in **Commento** digitare le informazioni che si desidera condividere con altri amministratori di sistema sulla configurazione.

6.  Fare clic su **Commit**.

7.  Ripetere i passaggi da 4 a 6 per ogni dominio di partner federato che si desidera consentire.

Per consentire l'accesso degli utenti federati, è inoltre necessario abilitare il supporto per l'accesso degli utenti federati nell'organizzazione. Per ulteriori informazioni, vedere [Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

È inoltre necessario configurare e applicare il criterio agli utenti per i quali si desidera consentire la collaborazione con gli utenti federati. Per ulteriori informazioni, vedere [Configure policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

