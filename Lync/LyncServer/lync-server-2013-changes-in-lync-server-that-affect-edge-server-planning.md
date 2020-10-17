---
title: 'Lync Server 2013: modifiche in Lync Server che influiscono sulla pianificazione del server perimetrale'
description: 'Lync Server 2013: modifiche in Lync Server che influiscono sulla pianificazione del server perimetrale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660a281d858cf92a48d5eaed6d5caf3141b3817
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543752"
---
# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Modifiche apportate in Lync Server 2013 che influiscono sulla pianificazione del server perimetrale

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Lync Server 2013 introduce nuove funzionalità che estendono le funzionalità e i metodi di comunicazione per gli utenti. Inoltre, Lync Server 2013 introduce modifiche ai servizi esistenti per migliorare l'integrazione e l'estensione dei servizi disponibili per l'organizzazione. Di seguito è riportato un riepilogo delle modifiche che possono influire sulla pianificazione e la distribuzione dei servizi server perimetrali di Lync Server 2013.

<div>

## <a name="support-for-ipv6-addressing"></a>Supporto dell'indirizzamento IPv6

Lync Server 2013 supporta l'indirizzamento IPv6 per tutti i servizi server perimetrali. Se sono stati forniti indirizzi IPv6 per le interfacce tramite la configurazione in Windows Server, è possibile utilizzare gli indirizzi IPv6 nella configurazione del server perimetrale tramite la configurazione degli indirizzi IP in Generatore di topologie. Inoltre, il protocollo XMPP (Extensible Messaging and Presence Protocol) supporta IPv6. Non è necessaria alcuna configurazione aggiuntiva. Se IPv6 è configurato nella topologia, XMPP utilizzerà IPv6 (se necessario).

Un ulteriore requisito per il supporto di IPv6 in Lync Server 2013 consiste nel creare record del sistema di nomi di dominio per i record che devono essere individuati e risolti in un indirizzo IPv6. Il sistema DNS IPv6 utilizza record host definiti **AAAA** e chiamati "quad-A". Gli altri tipi di record sono coerenti con le controparti IPv4.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>Supporto della distribuzione del protocollo XMPP (Extensible Messaging and Presence Protocol)

Server perimetrale introduce un proxy XMPP completamente integrato (distribuito sui server perimetrali) e un gateway XMPP (distribuito nei server front end). È possibile distribuire la federazione XMPP come componente facoltativo. Aggiungendo e configurando il proxy XMPP e il gateway XMPP, è possibile consentire agli utenti di Microsoft Lync 2013 di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.

<div>


> [!NOTE]  
> Attualmente, i servizi XMPP nel server perimetrale offrono solo la messaggistica istantanea e la presenza tra i client di Lync Server e i contatti basati su XMPP. Il protocollo XMPP, inoltre, è ospitato in un solo sito.



</div>

<div>


> [!IMPORTANT]  
> La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la federazione di messaggistica istantanea con Google Talk. Per altri sistemi XMPP, contattare il fornitore di terze parti per verificare l'eventuale supporto della federazione con Lync Server 2013 e per indicazioni per la distribuzione o la risoluzione dei problemi.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>Supporto della distribuzione di certificati di autenticazione audio/video e di autenticazione server-server

I certificati vengono utilizzati per generare token rilasciati ai client e altri consumer del servizio di autenticazione A/V e per l'autenticazione server-server. Il certificato di autenticazione audio/video è di tipo *AudioVideoAuthentication* e il certificato di autenticazione server-server è di tipo *OAuthTokenIssuer*.

Per l'autenticazione audio/video, i token vengono utilizzati per autenticare le richieste di allocazione della porta e vengono memorizzati nella cache per un massimo di 8 ore, ovvero la durata predefinita del token. In condizioni operative normali, questo è un metodo molto affidabile per creare e distribuire il materiale di autenticazione ai consumer del servizio A/V. I certificati, tuttavia, hanno una durata definita e una data e ora di scadenza prestabilite, in base alla data di creazione e ai criteri applicati dall'Autorità di certificazione che ha creato il certificato, solitamente 2 anni per questo tipo di certificato. Alla scadenza del certificato, qualsiasi token creato dal certificato scaduto e memorizzato nella cache dai consumer diventa non valido. Qualsiasi tentativo di utilizzare un token creato con un certificato scaduto risulterebbe in errori di allocazione Media Relay e causerebbe l'interruzione di qualsiasi sessione audio/video corrente. A questo punto, il client dovrebbe acquisire un nuovo token creato da un certificato valido per riprendere le normali funzionalità audio e video.

L'autenticazione da server a server è gestita da un certificato globale richiesto e applicato a tutti i server della distribuzione. Il certificato è responsabile dell'autenticazione dei server in Lync Server 2013, nonché dell'autenticazione in Exchange 2013 e Microsoft SharePoint Server 2013. Per ulteriori informazioni sul funzionamento dell'autenticazione da server a server, vedere [Managing server-to-Server Authentication (OAuth) and partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Una differenza molto importante tra il processo di autenticazione audio/video e il processo di autenticazione da server a server è la durata dell'autenticazione o dei token. Per l'autenticazione audio/video, l'autenticazione scade dopo otto ore. L'autenticazione da server a server ha una durata di 24 ore. È necessario pianificare di conseguenza per ognuno dei tipi di certificato.

New for Lync Server 2013 è la possibilità di eseguire il passaggio di un certificato di autenticazione audio/video sostitutivo e del certificato di autenticazione da server a server in anticipo rispetto alla scadenza del certificato corrente. Il nuovo certificato viene quindi utilizzato per la generazione di nuovi token o di nuove richieste di autenticazione. Tuttavia, il certificato precedente viene mantenuto per la verifica delle sessioni e delle autenticazioni correnti. Ciò che si ottiene è quello di prevenire efficacemente quasi tutti gli errori causati dalle scadenze dei token e dei certificati. Per informazioni dettagliate su questa funzionalità e su come configurarla, vedere [staging AV and OAuth Certificates in Lync Server 2013 using-roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Minore dipendenza dall'affinità basata su cookie

Nelle versioni precedenti di Lync Server e Office Communications Server, l'affinità basata su cookie veniva utilizzata dai servizi Web per garantire che lo stato della sessione dei servizi Web e del client venisse mantenuto. I servizi Web di Lync Server 2013 utilizzano un meccanismo di affinità incorporato che consente di eliminare la maggior parte dei requisiti per l'affinità basata su cookie.

<div>


> [!WARNING]  
> Il client Microsoft Lync 2010 mobile deve comunque utilizzare l'affinità basata su cookie e richiede la configurazione dell'affinità basata su cookie fino a quando non sono stati migrati tutti i client all'imminente client Microsoft Lync mobile (data di rilascio non ancora determinata).



</div>

Per informazioni dettagliate sull'affinità basata su cookie in Lync Server 2013, vedere [componenti necessari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).

</div>

<div>

## <a name="autodiscover-enhancements"></a>Miglioramenti dell'individuazione automatica

La funzionalità di individuazione automatica in Lync Server 2013 consente ai client di individuare altre funzionalità rese disponibili per la comunicazione. La funzionalità di individuazione automatica è stata introdotta per la prima volta nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011 per dispositivi mobili e Microsoft Lync 2010 mobile. La funzionalità di individuazione automatica, nota anche per i nomi dei record DNS LyncDiscover e LyncDiscoverInternal, consente ai client di individuare e utilizzare i servizi per dispositivi mobili (per i client Microsoft Lync 2010 Mobile), Microsoft Lync Web App e Lync Web Scheduler, nonché le comunicazioni con Microsoft Exchange Server e SharePoint Server. L'individuazione automatica viene installata come normale parte dell'installazione e della distribuzione dell'infrastruttura e dei server Lync Server 2013. Il generatore di topologie e la distribuzione guidata di Lync Server eliminano la maggior parte delle attività di configurazione necessarie per l'aggiornamento cumulativo per Lync Server 2010: novembre 2011.

</div>

<div>

## <a name="services-for-mobile-clients"></a>Servizi per i client mobili

Introdotti nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011, i servizi per dispositivi mobili in Lync Server 2013 consentono ai telefoni mobili che eseguono Lync mobile e tablet con dispositivi mobili supportati Apple iOS, Android, Windows Phone o Nokia per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza. Inoltre, i dispositivi mobili supportano alcune funzionalità di VoIP aziendale, ad esempio la partecipazione con un clic, Chiamata tramite ufficio, numero unico, segreteria telefonica e notifica delle chiamate senza risposta.

<div>


> [!NOTE]  
> I servizi di mobilità utilizzano il proxy inverso e i servizi pubblicati distribuiti nel Front End Server. Non sono necessarie modifiche per i server perimetrali. È necessario almeno in uscita SIP/TCP/5061from il server che esegue il servizio Access Edge di Lync Server.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>Il ruolo Director è facoltativo

Il ruolo del server Director nella topologia di Lync Server 2013 non è stato modificato. Ospita ancora servizi Web, preautentica le richieste degli utenti in arrivo e indirizza gli utenti esterni al proprio pool Home. Se si modifica il server Director da un ruolo consigliato a un ruolo facoltativo, Microsoft non intenderà diminuire il valore del server Director. L'intenzione è quella di ridurre il numero di server e altri requisiti hardware, ad esempio i servizi di bilanciamento del carico hardware per il Director, senza compromettere caratteristiche e funzionalità. Poiché i Front End Server possono eseguire lo stesso processo del Director senza alcun impatto sui servizi forniti, è possibile distribuire i direttori se lo si sceglie. È possibile escludere in modo sicuro il Director con la sicurezza che i Front End Server forniranno gli stessi servizi al posto di un Director.

</div>

</div>

<span> </span>

</div>

</div>

</div>

