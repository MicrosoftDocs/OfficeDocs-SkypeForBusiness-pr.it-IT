---
title: 'Lync Server 2013: Modifiche introdotte in Lync Server che incidono sulla pianificazione dei server perimetrali'
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
ms.openlocfilehash: 73eda15acbce7eb4b47a0a52602776e8fc830b0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Modifiche introdotte in Lync Server 2013 che incidono sulla pianificazione dei server perimetrali

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Lync Server 2013 introduce nuove funzionalità che estendono le caratteristiche e i metodi di comunicazione per gli utenti. Inoltre, Lync Server 2013 introduce le modifiche ai servizi esistenti per integrare meglio ed estendere i servizi disponibili per l'organizzazione. Di seguito è riportato un riepilogo delle modifiche che possono influenzare la pianificazione e la distribuzione dei servizi di Lync Server 2013 Edge Server.

<div>

## <a name="support-for-ipv6-addressing"></a>Supporto per l'indirizzamento IPv6

Lync Server 2013 supporta l'indirizzamento IPv6 per tutti i servizi Edge Server. Se sono stati forniti indirizzi IPv6 per le interfacce tramite la configurazione in Windows Server, è possibile usare gli indirizzi IPv6 nella configurazione del server perimetrale tramite la configurazione degli indirizzi IP in Generatore di topologie. Inoltre, il protocollo XMPP (Extensible Messaging and Presence Protocol) supporta IPv6. Non è necessaria alcuna configurazione aggiuntiva. Se IPv6 è configurato nella topologia, XMPP userà IPv6 (dove richiesto).

Un requisito aggiuntivo per supportare IPv6 in Lync Server 2013 consiste nel creare record di sistema di nomi di dominio per i record che devono essere individuati e risolti in un indirizzo IPv6. DNS IPv6 usa i record host definiti come **aaaa** e detti "Quad-A". Altri tipi di record sono coerenti con le rispettive controparti IPv4.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>Supporto per la distribuzione XMPP (Extensible Messaging and Presence Protocol)

Edge Server introduce un proxy XMPP completamente integrato (distribuito sugli Edge Server) e un gateway XMPP (distribuito nei server front-end). Puoi distribuire la Federazione XMPP come componente facoltativo. Aggiungendo e configurando il proxy XMPP e il gateway XMPP, è possibile consentire agli utenti di Microsoft Lync 2013 di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.

<div>


> [!NOTE]  
> Attualmente, i servizi XMPP in Edge Server consentono solo la messaggistica istantanea e la presenza tra i client Lync Server e i contatti basati su XMPP. Inoltre, XMPP è ospitato in un solo sito.



</div>

<div>


> [!IMPORTANT]  
> La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la Federazione della messaggistica istantanea con Google Talk. Per qualsiasi altro sistema XMPP, contattare il fornitore di terze parti per verificare che supportino la Federazione con Lync Server 2013 e per eventuali suggerimenti per la distribuzione o la risoluzione dei problemi.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>Supporto per l'autenticazione audio/video e i certificati di autenticazione server e server

Viene usato un certificato per generare i token emessi ai client e ad altri utenti del servizio di autenticazione A/V e per l'autenticazione da server a server. Il certificato di autenticazione audio/video è di tipo *AudioVideoAuthentication* e il certificato di autenticazione server-server è di tipo *OAuthTokenIssuer*.

Per l'autenticazione audio/video, i token vengono usati per autenticare le richieste di allocazione della porta e i token vengono memorizzati nella cache per un massimo di 8 ore, ovvero la durata predefinita del token. In funzionamento normale, si tratta di un metodo molto affidabile per creare e distribuire materiale di autenticazione ai consumer A/V. I certificati hanno tuttavia una durata limitata e scadono in una data e un'ora predefinite (in base alla data di creazione e ai criteri applicati all'autorità di certificazione che ha creato il certificato, in genere 2 anni per questo tipo di certificato). Quando il certificato scade, i token creati dal certificato scaduto e memorizzati nella cache dai consumatori diventano non validi. Qualsiasi tentativo di usare un token creato con un certificato scaduto comporterebbe l'assegnazione di allocazioni di relay multimediali non riuscite e le eventuali sessioni audio/video correnti avranno esito negativo. Il client dovrà acquisire un nuovo token creato da un certificato valido per riprendere le normali funzionalità audio e video.

L'autenticazione da server a server è gestita da un certificato globale richiesto e applicato a tutti i server della distribuzione. Il certificato è responsabile per l'autenticazione dei server in Lync Server 2013 e per l'autenticazione in Exchange 2013 e Microsoft SharePoint Server 2013. Per altre informazioni sul funzionamento dell'autenticazione da server a server, vedere [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Una differenza molto importante tra il processo di autenticazione audio/video e il processo di autenticazione da server a server è la durata dell'autenticazione o dei token. Per l'autenticazione audio/video, l'autenticazione scade dopo otto ore. L'autenticazione da server a server ha una durata di 24 ore. È necessario pianificare di conseguenza ogni tipo di certificato.

Novità di Lync Server 2013 è la possibilità di eseguire la fase di sostituzione del certificato di autenticazione audio/video e del server al certificato di autenticazione server in anticipo rispetto alla scadenza del certificato corrente. Il nuovo certificato viene quindi usato per generare nuovi token o nuove richieste di autenticazione. conserva però il vecchio certificato per la verifica delle sessioni e delle autenticazioni correnti. Il risultato è quello di impedire in modo efficace quasi tutti gli errori dovuti alla scadenza del token e del certificato. Per informazioni dettagliate su questa funzionalità e su come configurarla, vedere [staging di certificati AV e OAuth in Lync Server 2013 con-roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Dipendenza ridotta dall'affinità basata su cookie

Nelle versioni precedenti di Lync Server e Office Communications Server l'affinità basata su cookie è stata usata dai servizi Web per assicurarsi che lo stato della sessione client e servizi Web sia stato mantenuto. I servizi Web di Lync Server 2013 usano un meccanismo di affinità incorporato che elimina la maggior parte dei requisiti per l'affinità basata su cookie.

<div>


> [!WARNING]  
> Il client per dispositivi mobili Microsoft Lync 2010 deve comunque usare l'affinità basata su cookie e richiederà la configurazione dell'affinità basata su cookie finché non si esegue la migrazione di tutti i client al client Microsoft Lync Mobile imminente (data di rilascio non ancora determinato).



</div>

Per informazioni dettagliate sull'affinità basata su cookie in Lync Server 2013, vedere [componenti necessari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).

</div>

<div>

## <a name="autodiscover-enhancements"></a>Miglioramenti per l'individuazione automatica

La caratteristica di individuazione automatica in Lync Server 2013 consente ai client di individuare funzionalità aggiuntive messe a disposizione per la comunicazione. L'individuazione automatica è stata introdotta per la prima volta nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011 per la mobilità e Microsoft Lync 2010 mobile. La caratteristica di individuazione automatica (nota anche con i nomi dei record DNS LyncDiscover e LyncDiscoverInternal) consente ai client di individuare e usare i servizi di mobilità (per i client mobili Microsoft Lync 2010), Microsoft Lync Web App e Lync Web Scheduler, nonché comunicazioni con Microsoft Exchange Server e SharePoint Server. L'individuazione automatica viene installata come normale parte della configurazione e della distribuzione dell'infrastruttura e dei server di Lync Server 2013. Il generatore di topologia e la distribuzione guidata di Lync Server eliminano la maggior parte delle attività di configurazione necessarie in aggiornamento cumulativo per Lync Server 2010: novembre 2011.

</div>

<div>

## <a name="services-for-mobile-clients"></a>Servizi per i client mobili

Introdotta nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011, servizi di mobilità in Lync Server 2013 abilitare i telefoni cellulari che eseguono Lync mobile e tablet usando i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia da eseguire attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza. I dispositivi mobili supportano inoltre alcune funzionalità VoIP aziendale, ad esempio fare clic per partecipare a una conferenza, chiamare tramite lavoro, raggiungere un numero singolo, la segreteria telefonica e la notifica delle chiamate perse.

<div>


> [!NOTE]  
> I servizi di mobilità usano il proxy inverso e i servizi pubblicati distribuiti nei server front-end. Per Edge Server non sono necessarie modifiche. È necessario un collegamento SIP/TCP/5061from in uscita nel server che gestisce il servizio Access Edge di Lync Server.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>Il ruolo Director è facoltativo

Il ruolo del server Director nella topologia di Lync Server 2013 non è cambiato. Ospita ancora servizi Web, esegue la preautenticazione delle richieste utente in arrivo e indirizza gli utenti esterni al proprio pool Home. Modificando il Director da un ruolo consigliato a un ruolo facoltativo, Microsoft non intenderà diminuire il valore del Director. L'intenzione consiste nel ridurre il numero di server e altri requisiti hardware, ad esempio i servizi di bilanciamento del carico hardware per il Director, senza compromettere caratteristiche e funzionalità. Dato che i server front-end possono eseguire lo stesso processo di Director senza alcun impatto sui servizi forniti, è possibile distribuire direttori se si sceglie di. È possibile escludere in modo sicuro il Director con sicurezza che i server front-end forniranno gli stessi servizi al posto di un amministratore.

</div>

</div>

<span> </span>

</div>

</div>

</div>

