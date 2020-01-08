---
title: 'Lync Server 2013: Configurare il supporto per i domini esterni bloccati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08191e8600f5e247ba6b4a358557ea3def0a1756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Configurare il supporto per i domini esterni bloccati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Se è stato configurato il supporto per i partner federati, è possibile gestire i domini che verranno bloccati dalla Federazione con l'organizzazione. L'elenco dei domini bloccati fungerà da elenco di blocchi (elenco delle voci esplicite che non devono essere consentite) e verrà applicato nell'individuazione di domini federati, se questa opzione è abilitata. Per informazioni dettagliate, vedere [abilitare o disabilitare l'individuazione dei partner federativi in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Bloccare uno o più domini esterni dalla connessione alla propria organizzazione. A questo scopo, Aggiungi il dominio all'elenco dei domini bloccati.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Per aggiungere un dominio esterno all'elenco dei domini bloccati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**.

4.  Fare clic su **domini federati**, su **nuovo**e quindi su **dominio bloccato**.

5.  In **nuovi domini federati**eseguire le operazioni seguenti:
    
      - In **Domain Name (o FQDN)** Digitare il nome del dominio del partner federato che si vuole bloccare.
        
        <div>
        

        > [!NOTE]  
        > Il nome non può superare i 256 caratteri di lunghezza.<BR>La ricerca nel nome di dominio del partner federativo esegue una corrispondenza con suffisso. Ad esempio, se si digita <STRONG>contoso.com</STRONG>, la ricerca restituirà anche il dominio <STRONG>it.contoso.com</STRONG>.<BR>Un dominio partner federato non può essere bloccato e consentito simultaneamente. Lync Server 2013 impedisce che ciò avvenga in modo da non dover sincronizzare gli elenchi.

        
        </div>
    
      - Opzionale In **Commento**Digitare le informazioni che si desidera condividere con altri amministratori di sistema su questa configurazione.

6.  Fare clic su **Commit**.

7.  Ripetere i passaggi da 4 a 6 per ogni partner federato che si vuole bloccare.

Per abilitare l'accesso degli utenti federati, devi anche abilitare il supporto per l'accesso degli utenti federati nell'organizzazione. Per informazioni dettagliate, vedere [abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Inoltre, è necessario configurare e applicare il criterio agli utenti che si vuole poter collaborare con gli utenti federati. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti federati in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

