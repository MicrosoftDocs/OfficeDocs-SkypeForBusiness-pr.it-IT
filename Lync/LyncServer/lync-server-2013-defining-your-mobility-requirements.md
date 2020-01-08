---
title: 'Lync Server 2013: Definizione dei requisiti per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 604812d96f58a53ee008bfe42603243571138d1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Definizione dei requisiti per dispositivi mobili per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Durante la fase di pianificazione della funzionalità di mobilità di Lync Server 2013, quando si usano client mobili Lync 2010 mobile e Lync 2013, è possibile prendere decisioni che determinano la procedura di distribuzione.

Ecco le decisioni che devi prendere in considerazione:

  - **Si vuole usare l'individuazione automatica per i client mobili Lync?**
    
    Se si vuole supportare l'individuazione automatica, è necessario creare nuovi record DNS (Domain Name System) interni ed esterni, aggiungere nomi alternativi soggetti ai certificati nei server front-end, direttori e proxy inverso e modificare le regole di pubblicazione esistenti. nel proxy inverso. Per informazioni dettagliate, vedere [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Con l'individuazione automatica, gli utenti possono individuare automaticamente i servizi Web di Lync Server 2013 ovunque all'interno o all'esterno della rete aziendale, senza immettere URL nelle impostazioni del dispositivo mobile.
    
    Se si usano le impostazioni manuali anziché l'individuazione automatica, gli utenti mobili devono immettere manualmente gli URL seguenti nei propri dispositivi mobili:
    
      - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root per l'accesso esterno
    
      - https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice. svc/root per l'accesso interno
    
    Ti consigliamo vivamente di usare l'individuazione automatica. L'uso principale delle impostazioni manuali è per la risoluzione dei problemi.

  - **Se si decide di supportare l'individuazione automatica, si è disposti ad aggiornare i certificati nel proxy inverso con i nomi alternativi oggetto per ogni dominio SIP?**
    
    Se si hanno molti domini SIP, l'aggiornamento dei certificati pubblici al proxy inverso può diventare molto costoso. In questo caso, puoi scegliere di implementare il rilevamento automatico in modo che la richiesta di servizio di individuazione automatica usi HTTP sulla porta 80, invece di usare HTTPS sulla porta 443. Tuttavia, questo non è l'approccio consigliato. Se si decide di scegliere questa alternativa, non è necessario aggiornare i certificati nel proxy inverso, ma è necessario creare una regola di pubblicazione Web per HTTP sulla porta 80. Per altri dettagli, vedere [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Si desidera supportare i client di Lync mobile sia interni che esterni alla rete aziendale o supportare i client solo all'interno della rete aziendale?**
    
    Se si vuole supportare i client mobili interni ed esterni alla rete, i dispositivi mobili possono accedere alle caratteristiche di mobilità da qualsiasi posizione. La configurazione predefinita consiste nel supportare i client interni ed esterni alla rete aziendale.
    
    Anche se la configurazione predefinita consente al traffico client mobile di passare attraverso il sito esterno, è possibile limitare il traffico client per dispositivi mobili alla rete aziendale interna. Quando si limita il traffico alla rete interna, gli utenti possono usare le applicazioni mobili di Lync nei propri dispositivi mobili solo quando si trovano all'interno della rete.
    
    Per le distribuzioni che supportano la mobilità tramite il servizio di mobilità MCX e Lync 2010 mobile, è possibile eseguire il cmdlet **Set-CsMcxConfiguration** . Per impostare la mobilità solo per uso interno, è possibile usare un comando simile al seguente:
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > Non sono necessarie altre configurazioni per UCWA. UCWA non ha una configurazione solo interna equivalente.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Se si usa un server front-end&nbsp;di lync Server 2013 o i pool Front-end e <STRONG>non si dispone</STRONG> di server&nbsp;front end o pool front-end di Lync Server 2010, non <STRONG>è necessario alcun requisito di persistenza basato su cookie</STRONG>. Se è necessario mantenere tutti i server front end&nbsp;o i pool Front End di lync Server 2010, le stesse regole si applicano ancora come in Lync Server 2010 per la persistenza basata su cookie.

    
    </div>

  - **Si desidera supportare le notifiche push per i dispositivi Apple iOS e i telefoni Windows?**
    
    Se si supportano le notifiche push, i dispositivi iOS Apple supportati e i telefoni Windows ricevono una notifica degli eventi che si verificano quando l'applicazione per dispositivi mobili è inattiva. È necessario configurare l'Edge Server per avere una relazione federativa con il servizio di notifica push di Lync Server basato su cloud, disponibile nel centro dati di Lync Online, ed eseguire un cmdlet per abilitare le notifiche push.
    
    Se si vuole supportare le notifiche push tramite la rete Wi-Fi, oltre a supportare le notifiche push tramite le reti 3G o dati dei provider di dispositivi mobili, è necessario aprire la porta 5223 in uscita nella rete Wi-Fi aziendale. Il supporto delle notifiche push tramite la rete Wi-Fi supporta i dispositivi mobili che usano solo Wi-Fi e dispositivi mobili con scarsa ricezione interna.
    
    <div>
    

    > [!IMPORTANT]  
    > La porta di apertura TCP 5223 è necessaria solo quando si supportano dispositivi Apple che gestiscono il client mobile Lync 2010.

    
    </div>
    
    Se non si supportano le notifiche push, gli utenti dei dispositivi mobili Apple e i telefoni Windows non informano sugli eventi, ad esempio gli inviti di messaggi istantanei o i messaggi persi, che si verificano quando l'applicazione per dispositivi mobili non è attiva.
    
    <div>
    

    > [!NOTE]  
    > I client mobili Lync 2013 nei dispositivi Apple non richiedono notifiche push. I client per dispositivi mobili Lync 2013 in Windows Phone usano la notifica push. La pianificazione della notifica push e la funzione di compensazione delle notifiche push rimangono le stesse per Lync Mobile su dispositivi Windows Phone e Apple che non sono in grado di eseguire il client per dispositivi mobili Lync 2013.

    
    </div>

  - **Si vuole consentire a tutti gli utenti di accedere alle caratteristiche di mobilità oppure si vuole essere in grado di specificare quali utenti hanno accesso a queste funzionalità?**
    
    La tabella descrive le funzionalità disponibili per gli utenti in Lync Server 2013. Le impostazioni predefinite consentono la chiamata tramite lavoro, Consenti VoIP (Voice over IP) e Abilita mobilità. Ecco il set completo di opzioni disponibili:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Caratteristica/nome parametro/ambito (i nomi dei parametri di criteri potrebbero non essere uguali)</th>
    <th>Descrizione</th>
    <th>Introdotto</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Abilitare la mobilità</p>
    <p>Nome parametro:<code>EnableMobility</code></p>
    <p>Ambito: globale/sito/utente</p></td>
    <td><p>Impostazione amministrativa per controllare gli utenti in un ambito specifico in cui è installato Lync mobile, se il criterio è impostato su false, l'utente non potrà accedere al client.</p>
    <p>L'impostazione predefinita è true.</p></td>
    <td><p>Aggiornamento cumulativo per Lync Server 2010: novembre 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>Abilitare la voce esterna</p>
    <p>Nome parametro:<code>EnableOutsideVoice</code></p>
    <p>Ambito: globale/sito/utente</p></td>
    <td><p>Controlla la possibilità di un utente di usare la chiamata tramite il lavoro, una caratteristica che consente agli utenti di effettuare e ricevere chiamate usando il loro numero di lavoro anziché il numero di cellulare. Se impostato su false, l'utente non sarà in grado di effettuare o ricevere chiamate usando il proprio numero di lavoro dal dispositivo mobile.</p>
    <p>L'impostazione predefinita è true</p></td>
    <td><p>Aggiornamento cumulativo per Lync Server 2010: novembre 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>Abilitare l'audio e il video IP</p>
    <p>Nome parametro:<code>EnableIPAudioVideo</code></p>
    <p>Ambito: globale/sito/utente</p></td>
    <td><p>Controlla se un utente può usare il VoIP per effettuare o ricevere chiamate vocali o video nel dispositivo mobile. Se impostato su false, l'utente non sarà in grado di effettuare o ricevere chiamate VoIP o video sul dispositivo.</p>
    <p>L'impostazione predefinita è true.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Richiedi Wi-Fi per l'audio IP</p>
    <p>Nome parametro:<code>RequireWiFiForIPAudio</code></p>
    <p>Ambito: globale/sito/utente</p></td>
    <td><p>Questa impostazione definisce se il client verrà richiesto di effettuare e ricevere chiamate tramite VoIP su WiFi invece della rete dati cellulare. Se impostato su true, l'utente può effettuare e ricevere chiamate VoIP solo quando si è connessi a una rete Wi-Fi.</p>
    <p>L'impostazione predefinita è false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Richiedi Wi-Fi per IP video</p>
    <p>Nome parametro:<code>RequireWiFiForIPVideo</code></p>
    <p>Ambito: globale/sito/utente</p></td>
    <td><p>Questa impostazione definisce se il client sarà necessario per effettuare e ricevere videochiamate su Wi-Fi anziché sulla rete di dati del cellulare. Se impostato su true, l'utente può effettuare e ricevere videochiamate solo quando si è connessi a una rete Wi-Fi.</p>
    <p>L'impostazione predefinita è false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Per una descrizione delle impostazioni dei criteri che è possibile configurare e come gestire i criteri, vedere [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) e [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).

  - **Si desidera che gli utenti che non sono abilitati per VoIP aziendale possano usare il comando fai clic per partecipare alle conferenze?**
    
    Per consentire agli utenti di accedere alle caratteristiche di mobilità e chiamarle tramite lavoro, è necessario che siano abilitate per VoIP aziendale. Tuttavia, gli utenti non abilitati per VoIP aziendale possono partecipare a conferenze facendo clic sul collegamento nel dispositivo mobile, se hanno un criterio vocale appropriato assegnato. È possibile assegnare un criterio vocale specifico a questi utenti o verificare che esista un criterio globale o dei criteri a livello di sito che si applicano a tali criteri. Il criterio vocale assegnato deve avere record di utilizzo PSTN (Public Switched Telephone Network) e route che definiscono le aree a cui gli utenti possono effettuare la chiamata per partecipare a una conferenza. Per informazioni dettagliate sull'impostazione di criteri vocali, record di utilizzo PSTN e route, vedere [configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    
    <div>
    

    > [!NOTE]  
    > Gli utenti di dispositivi mobili che vogliono usare click to join richiedono un criterio vocale, insieme ai record di utilizzo PSTN correlati e alle route vocali, perché fare clic sul collegamento nel dispositivo mobile comporta una chiamata in uscita da Lync Server 2013.

    
    </div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  


[Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

