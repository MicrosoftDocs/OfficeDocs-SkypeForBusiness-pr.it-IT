---
title: 'Lync Server 2013: Configurare il supporto per i domini esterni consentiti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfab1a41f39d975d2920bdf97ea601618277f35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Configurare il supporto per i domini esterni consentiti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Se è stato configurato il supporto per i partner federati, è possibile gestire i domini specifici che possono essere federati con l'organizzazione. Si configurano uno o più domini esterni specifici come consentiti domini federati. A questo scopo, Aggiungi ogni dominio all'elenco dei domini consentiti. Anche se l'individuazione dei partner è abilitata per l'organizzazione, eseguire questa operazione se il dominio è un partner federato che potrebbe essere necessario comunicare con più di 1.000 degli utenti o potrebbe essere necessario inviare più di 20 messaggi al secondo. Se l'individuazione dei partner non è abilitata per l'organizzazione, solo gli utenti di domini esterni aggiunti all'elenco dei domini consentiti possono partecipare alla messaggistica istantanea e alle conferenze con gli utenti dell'organizzazione. Se si vuole limitare l'accesso a un dominio federato a un server specifico che usa il servizio Access Edge del partner federato, è possibile specificare il nome di dominio del server che usa il servizio Access Edge per ogni dominio nell'elenco dei domini consentiti.

<div>


> [!NOTE]  
> Questa procedura descrive come configurare il supporto per specifici domini, ma l'implementazione del supporto per gli utenti federati richiede anche l'abilitazione del supporto per gli utenti federati per l'organizzazione e la configurazione e l'applicazione di criteri per il controllo degli utenti che possono collaborare con gli utenti federati. Per informazioni dettagliate sull'abilitazione del supporto per gli utenti federati, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">abilitare o disabilitare l'accesso da utenti remoti in Lync Server 2013</A>. Per informazioni dettagliate sulla configurazione dei criteri per il controllo della Federazione, vedere <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configurare i criteri per controllare l'accesso degli utenti federati in Lync Server 2013</A>.



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Per aggiungere un dominio esterno all'elenco dei domini consentiti

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **domini federati**.

4.  Nella pagina **domini federati** fare clic su **nuovo**e quindi su **dominio consentito**.

5.  In **nuovi domini federati**eseguire le operazioni seguenti:
    
      - In **Domain Name (o FQDN)** Digitare il nome del dominio del partner federato.
        
        <div>
        

        > [!NOTE]  
        > Questo nome deve essere univoco e non può essere già presente come dominio consentito per il server che ha eseguito il servizio Access Edge. Il nome non può superare i 256 caratteri di lunghezza.<BR>La ricerca nel nome di dominio del partner federativo esegue una corrispondenza con suffisso. Ad esempio, se si digita <STRONG>contoso.com</STRONG>, la ricerca restituirà anche il dominio <STRONG>it.contoso.com</STRONG>.<BR>Un dominio partner federato non può essere bloccato e consentito simultaneamente. Lync Server 2013 impedisce che ciò avvenga in modo da non dover sincronizzare gli elenchi.

        
        </div>
    
      - Se si vuole limitare l'accesso per il dominio federato agli utenti di un server specifico che ha eseguito il servizio Access Edge, in **Access Edge Services (FQDN)** Digitare il nome di dominio completo del server del dominio federato in cui è in uso il servizio Access Edge.
    
      - Se si vogliono aggiungere altre informazioni, in **Commento**Digitare le informazioni che si desidera condividere con altri amministratori di sistema su questa configurazione.

6.  Fare clic su **Commit**.

7.  Ripetere i passaggi da 4 a 6 per ogni dominio di partner federato che si vuole consentire.

Per abilitare l'accesso degli utenti federati, devi anche abilitare il supporto per l'accesso degli utenti federati nell'organizzazione. Per informazioni dettagliate, vedere [abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Inoltre, è necessario configurare e applicare il criterio agli utenti che si vuole poter collaborare con gli utenti federati. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti federati in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

