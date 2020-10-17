---
title: 'Lync Server 2013: definizione dei requisiti per dispositivi mobili'
description: 'Lync Server 2013: definizione dei requisiti per dispositivi mobili.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fbc1a443946f0c879397f41628cfe788b428ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545542"
---
# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Definizione dei requisiti per dispositivi mobili per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Durante la fase di pianificazione per la funzionalità di mobilità di Lync Server 2013, quando si utilizzano i client mobili Lync 2010 mobile e Lync 2013, è possibile prendere decisioni che determinano i passaggi di distribuzione.

Di seguito sono riportate le decisioni che è necessario prendere in considerazione:

  - **Utilizzo dell'individuazione automatica per i client mobili di Lync**
    
    Se si desidera supportare l'individuazione automatica, è necessario creare nuovi record DNS (Domain Name System) interni ed esterni, aggiungere nomi alternativi del soggetto ai certificati nei Front End Server, ai direttori e al proxy inverso e modificare le regole di pubblicazione esistenti sul proxy inverso. Per informazioni dettagliate, vedere [requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Con l'individuazione automatica, gli utenti possono individuare automaticamente i servizi Web di Lync Server 2013 da qualsiasi posizione all'interno o all'esterno della rete aziendale, senza immettere gli URL nelle impostazioni dei dispositivi mobili.
    
    Se si utilizzano le impostazioni manuali invece dell'individuazione automatica, gli utenti mobili devono immettere manualmente gli URL seguenti nei propri dispositivi mobili:
    
      - \<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root https://per l'accesso esterno
    
      - https:// \<IntPoolFQDN\> /Autodiscover/autodiscoverservice. svc/root per l'accesso interno
    
    È consigliabile utilizzare l'individuazione automatica. Le impostazioni manuali devono essere utilizzate principalmente per attività di risoluzione dei problemi.

  - **Se si decide di supportare l'individuazione automatica, aggiornamento dei certificati nel proxy inverso con nomi alternativi soggetto per ogni dominio SIP**
    
    In presenza di numerosi domini SIP, l'aggiornamento dei certificati pubblici nel proxy inverso può diventare molto oneroso. In caso affermativo, è possibile scegliere di implementare l'individuazione automatica in modo che la richiesta di servizio di Autodiscover iniziale utilizzi HTTP sulla porta 80, anziché utilizzare HTTPS sulla porta 443. Tuttavia, questo non è l'approccio consigliato. Se si decide di scegliere questa alternativa, non è necessario aggiornare i certificati per il proxy inverso, ma è necessario creare una regola di pubblicazione Web per HTTP sulla porta 80. Per ulteriori informazioni, vedere [requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Supporto di client mobili di Lync sia all'interno che all'esterno della rete aziendale o solo all'interno**
    
    Se si desidera supportare client mobili interni ed esterni alla rete, i dispositivi mobili possono accedere alle funzionalità di mobilità da qualsiasi posizione. La configurazione predefinita prevede il supporto di client sia all'interno che all'esterno della rete aziendale.
    
    Sebbene la configurazione predefinita consenta il trasferimento del traffico client mobile al sito esterno, è possibile limitare questo traffico alla rete aziendale interna. In questo caso, gli utenti possono utilizzare le applicazioni mobili di Lync nei dispositivi mobili solo quando si trovano all'interno della rete.
    
    Per le distribuzioni che supportano la mobilità tramite il servizio per dispositivi mobili MCX e Lync 2010 mobile, è possibile eseguire il cmdlet **Set-CsMcxConfiguration** . Per impostare la mobilità solo per uso interno, è necessario utilizzare un comando simile al seguente:
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > Per UCWA non sono necessarie ulteriori configurazioni. UCWA non dispone di una configurazione equivalente solo interna.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Se si utilizza un server front-end di Lync Server 2013 &nbsp; o pool Front end e <STRONG>non si dispone</STRONG> di Lync Server 2010 &nbsp; front end server o pool Front End, non <STRONG>vi sono requisiti per la persistenza basata su cookie</STRONG>. Se è necessario mantenere tutti &nbsp; i server front end o i pool Front-End di Lync server 2010, le stesse regole vengono ancora applicate come in Lync Server 2010 per la persistenza basata su cookie.

    
    </div>

  - **Supporto delle notifiche push per dispositivi Apple iOS e Windows Phone**
    
    Se si supportano notifiche push, i dispositivi Apple iOS e Windows Phone supportati riceveranno una notifica degli eventi che si verificano quando l'applicazione mobile è inattiva. È necessario configurare il server perimetrale in modo che disponga di una relazione di federazione con il servizio di notifica push di Lync Server basato sul cloud, che si trova nel centro dati di Lync Online, ed esegua un cmdlet per abilitare le notifiche push.
    
    Se si desidera supportare le notifiche push tramite la rete di Wi-Fi, oltre a supportare le notifiche push tramite i provider di dispositivi mobili o le reti di dati, è necessario aprire la porta 5223 in uscita sulla rete aziendale Wi-Fi. L'utilizzo delle notifiche push sulla rete Wi-Fi consente di supportare dispositivi mobili che utilizzano solo Wi-Fi e dispositivi mobili con una ricezione di scarsa qualità in ambienti chiusi.
    
    <div>
    

    > [!IMPORTANT]  
    > La porta di apertura TCP 5223 è necessaria solo quando si supportano i dispositivi Apple che eseguono il client per dispositivi mobili Lync 2010.

    
    </div>
    
    Se non si supportano le notifiche push, gli utenti di dispositivi mobili Apple e Windows Phone non troveranno gli eventi, ad esempio gli inviti di messaggi istantanei o i messaggi mancati, che si verificano quando l'applicazione per dispositivi mobili non è attiva.
    
    <div>
    

    > [!NOTE]  
    > I client Lync 2013 mobile nei dispositivi Apple non richiedono notifiche push. I client Lync 2013 per dispositivi mobili su Windows Phone utilizzano la notifica push. La pianificazione della notifica push e la compensazione notifiche push rimangono invariate per Lync mobile nei dispositivi Windows Phone e Apple che non sono in grado di eseguire il client di telefonia mobile Lync 2013.

    
    </div>

  - **Si desidera consentire a tutti gli utenti di accedere alle funzionalità per dispositivi mobili oppure si desidera specificare quali utenti possono accedere a queste funzionalità?**
    
    La tabella descrive le funzionalità disponibili per gli utenti in Lync Server 2013. Le impostazioni predefinite consentono la chiamata tramite lavoro, consentono la funzionalità VoIP (Voice over IP) e consentono la mobilità. Di seguito è indicato il set completo di opzioni disponibili:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Caratteristica/nome parametro/ambito (i nomi di parametri dei criteri potrebbero non essere uguali)</th>
    <th>Descrizione</th>
    <th>Introdotta</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Abilitare la mobilità</p>
    <p>Nome del parametro: <code>EnableMobility</code></p>
    <p>Ambito: globale/sito/utente</p></td>
    <td><p>Impostazione amministrativa per controllare gli utenti in un determinato ambito in cui è installato Lync mobile, se il criterio è impostato su false, l'utente non sarà in grado di accedere al client.</p>
    <p>L'impostazione predefinita è true.</p></td>
    <td><p>Aggiornamento cumulativo per Lync Server 2010: novembre 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>Abilita voce esterna</p>
    <p>Nome del parametro: <code>EnableOutsideVoice</code></p>
    <p>Ambito: globale/sito/utente</p></td>
    <td><p>Controlla la capacità di un utente di utilizzare la chiamata tramite il lavoro, caratteristica che consente agli utenti di effettuare e ricevere chiamate utilizzando il numero di lavoro invece del numero di cellulare. Se il valore è impostato su false, l'utente non sarà in grado di effettuare o ricevere chiamate usando il proprio numero di lavoro dal proprio dispositivo mobile.</p>
    <p>L'impostazione predefinita è true</p></td>
    <td><p>Aggiornamento cumulativo per Lync Server 2010: novembre 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>Abilitare l'audio e il video IP</p>
    <p>Nome del parametro: <code>EnableIPAudioVideo</code></p>
    <p>Ambito: globale/sito/utente</p></td>
    <td><p>Controlla se un utente può usare il VoIP per effettuare o ricevere chiamate vocali o video sul proprio dispositivo mobile. Se il valore è impostato su false, l'utente non sarà in grado di effettuare o ricevere chiamate video o VoIP sul proprio dispositivo.</p>
    <p>L'impostazione predefinita è true.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Richiedi WiFi per l'audio IP</p>
    <p>Nome del parametro: <code>RequireWiFiForIPAudio</code></p>
    <p>Ambito: globale/sito/utente</p></td>
    <td><p>Questa impostazione consente di definire se il client sarà tenuto a effettuare e ricevere chiamate tramite VoIP su WiFi anziché sulla rete di dati cellulare. Se impostato su true, l'utente può effettuare e ricevere chiamate VoIP solo quando si è connessi a una rete Wi-Fi.</p>
    <p>L'impostazione predefinita è False.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Richiedi il WiFi per IP video</p>
    <p>Nome del parametro: <code>RequireWiFiForIPVideo</code></p>
    <p>Ambito: globale/sito/utente</p></td>
    <td><p>Questa impostazione consente di definire se il client sarà tenuto a effettuare e ricevere chiamate video su Wi-Fi invece che sulla rete di dati cellulare. Se impostato su true, l'utente può effettuare e ricevere chiamate video solo quando si è connessi a una rete Wi-Fi.</p>
    <p>L'impostazione predefinita è False.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Per una descrizione delle impostazioni dei criteri che è possibile configurare e come gestire i criteri, vedere [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) e [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).

  - **Partecipazione alle conferenze con un clic da parte degli utenti non abilitati per VoIP aziendale**
    
    Per poter accedere alle funzionalità di mobilità e Chiama di ufficio, gli utenti devono essere abilitati per VoIP aziendale. Tuttavia, gli utenti che non sono abilitati per VoIP aziendale possono partecipare a conferenze facendo clic sul collegamento sul dispositivo mobile, se dispongono di un criterio vocale appropriato assegnato. È possibile assegnare un criterio vocale specifico a questi utenti o verificare che esistano criteri globali o di criterio a livello di sito che si applicano a tali criteri. Il criterio vocale assegnato deve disporre dei record di utilizzo della rete PSTN (Public Switched Telephone Network) e delle route che definiscono le aree in cui gli utenti possono effettuare chiamate in uscita per partecipare a una conferenza. Per informazioni dettagliate sull'impostazione di criteri vocali, record di utilizzo PSTN e route, vedere [configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    
    <div>
    

    > [!NOTE]  
    > Gli utenti mobili che desiderano utilizzare fare clic su join richiedono un criterio vocale, insieme ai record di utilizzo PSTN correlati e alle route vocali, in quanto facendo clic sul collegamento sul dispositivo mobile si produce una chiamata in uscita da Lync Server 2013.

    
    </div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  


[Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

