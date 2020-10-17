---
title: 'Lync Server 2013: configurare il supporto per i domini esterni bloccati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be998071bc0cad49d3e96c3c82cf395b2da7ca1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515683"
---
# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Configurare il supporto per i domini esterni bloccati in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

Se il supporto per i partner federati è configurato, è possibile gestire i domini ai quali impedire di federarsi con l'organizzazione. L'elenco dei domini bloccati svolgerà la funzione di elenco blocchi (elenco di una serie di voci esplicite da non consentire) e verrà applicato nell'individuazione di domini federati, se questa opzione è abilitata. Per informazioni dettagliate, vedere [Abilitazione o disabilitazione dell'individuazione dei partner federativi in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Impedire a uno o più domini esterni di connettersi all'organizzazione. A tale scopo, aggiungere il dominio all'elenco dei domini bloccati.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Per aggiungere un dominio esterno all'elenco dei domini bloccati

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Accesso utente esterno**.

4.  Fare clic su **Domini federati**, su **Nuovo** e quindi su **Dominio bloccato**.

5.  In **Nuovi domini federati** eseguire le operazioni seguenti:
    
      - In **Nome di dominio (o FQDN)** digitare il nome del dominio del partner federato che si desidera bloccare.
        
        <div>
        

        > [!NOTE]  
        > Il nome può essere costituito da un massimo di 256 caratteri.<BR>La ricerca in base al nome di dominio del partner federato si basa sulla corrispondenza del suffisso. Se ad esempio si digita <STRONG>contoso.com</STRONG>, la ricerca restituirà anche il dominio <STRONG>it.contoso.com</STRONG>.<BR>Un dominio di partner federato non può essere contemporaneamente bloccato e consentito. Lync Server 2013 impedisce l'avvenuto verificarsi in modo da non dover sincronizzare gli elenchi.

        
        </div>
    
      - (Facoltativo) In **Commento** digitare le informazioni che si desidera condividere con gli altri amministratori di sistema su questa configurazione.

6.  Fare clic su **Commit**.

7.  Ripetere i passaggi da 4 a 6 per ogni partner federato che si desidera bloccare.

Per consentire l'accesso degli utenti federati, è inoltre necessario abilitare il supporto per l'accesso degli utenti federati nell'organizzazione. Per ulteriori informazioni, vedere [Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

È inoltre necessario configurare e applicare il criterio agli utenti per i quali si desidera consentire la collaborazione con gli utenti federati. Per ulteriori informazioni, vedere [Configure policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

