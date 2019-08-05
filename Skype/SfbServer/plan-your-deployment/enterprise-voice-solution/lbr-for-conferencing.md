---
title: Routing basato sulla posizione per i servizi di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Pianificazione del routing basato sulla posizione per i servizi di conferenza in Skype for Business Server VoIP aziendale, inclusi i trasferimenti delle chiamate consultive.
ms.openlocfilehash: d9ca03920fe361cf4d7692fd80031bef01b03b17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187661"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Routing basato sulla posizione per i servizi di conferenza in Skype for Business Server

Pianificazione del routing basato sulla posizione per i servizi di conferenza in Skype for Business Server VoIP aziendale, inclusi i trasferimenti delle chiamate consultive.

Il routing basato sulla posizione consente di limitare il routing delle chiamate tra endpoint VoIP e endpoint PSTN in base alla posizione delle parti nella chiamata. Il routing basato sulla posizione per i servizi di conferenza consente di applicare regole di routing basate sulla posizione per le riunioni (ad esempio conferenze) per impedire l'esclusione del pedaggio PSTN. L'applicazione monitora una conferenza attiva e applica restrizioni di routing basate sulla posizione in base alla posizione degli utenti partecipanti. L'applicazione di routing basata sulla posizione per le conferenze consente inoltre di applicare le restrizioni di routing basate sulla posizione ai trasferimenti consultivi che coinvolgono endpoint PSTN.

L'applicazione per i servizi di conferenza di routing basato sulla posizione offre a conferenze Skype for business un meccanismo per la prevenzione del bypass a pedaggio PSTN. L'applicazione monitora le conferenze attive e applica le restrizioni di routing basate sulla posizione in base alla posizione degli utenti di Skype for business partecipanti.

L'applicazione per i servizi di conferenza di routing basato sulla posizione determina se il routing basato sulla posizione deve essere applicato in una riunione Skype for business se vengono soddisfatti i criteri seguenti:

- L'organizzatore della riunione è abilitato per il routing basato sulla posizione. Le restrizioni di routing basate sul percorso verranno applicate solo alle conferenze organizzate dagli utenti abilitati per il routing basato sulla posizione.

- Almeno un partecipante alla riunione è un endpoint PSTN. Le restrizioni di routing basate sulla posizione sono applicabili solo per le conferenze che includono endpoint PSTN.

- Sito di rete in cui si trova il gateway PSTN usato per il Bridge della conferenza alla rete PSTN, nonché i siti di Network in cui gli organizzatori e i partecipanti sono connessi.

L'applicazione di routing basata sulla posizione per le conferenze impedisce la partecipazione degli utenti di Skype for business e degli endpoint PSTN provenienti da siti di rete diversi alla stessa conferenza. Se l'organizzatore di una riunione è abilitato per il routing basato sulla posizione, l'applicazione di conferenza applica le restrizioni seguenti:

- Gli endpoint che possono partecipare a una riunione Skype for business dipendono dagli endpoint che hanno già partecipato alla conferenza e questa restrizione viene regolata con l'uscita degli endpoint Uniti e i nuovi endpoint partecipano alla conferenza. Se gli organizzatori e i partecipanti partecipano a una riunione Skype for business dallo stesso sito di rete, un endpoint PSTN, un altro partecipante dello stesso sito di rete, un altro partecipante proveniente da un sito di rete diverso o da un partecipante di un sito di rete sconosciuto possono partecipare.

- Se gli organizzatori e i partecipanti partecipano alla riunione da siti di rete diversi o sconosciuti, non è consentito l'accesso alla riunione da parte di un endpoint PSTN se la chiamata PSTN entra da un trunk SIP abilitato per il routing basato sulla posizione.

- Se gli organizzatori e i partecipanti partecipano alla riunione dallo stesso sito di rete e i partecipanti partecipano alla stessa riunione da PSTN, non è consentito partecipare alla riunione con un endpoint di Skype for business da un sito di rete diverso.

Queste restrizioni di routing basate sulla posizione dei servizi di conferenza sono riepilogate nella tabella seguente.

| |

|**Utenti in una conferenza in un dato punto**|**Utenti autorizzati a partecipare alla conferenza**|**Utenti non autorizzati a partecipare alla conferenza**|
|:-----|:-----|:-----|
|Utenti del client VoIP di Skype for business da un singolo sito di rete  <br/> |Utente client VoIP di Skype for business dello stesso sito di rete  <br/> Utente client VoIP di Skype for business da un sito di rete diverso  <br/> Utente client VoIP di Skype for business da un sito di rete sconosciuto  <br/> Utente client VoIP di Skype for business federativo  <br/> Aggiunta di un utente da un endpoint PSTN  <br/> |Nessuno  <br/> |
|Utenti del client VoIP di Skype for business da un sito di rete sconosciuto  <br/> |Utente client VoIP di Skype for business da qualsiasi sito  <br/> Utente client VoIP di Skype for business da un sito sconosciuto  <br/> Utente client VoIP di Skype for business federativo  <br/> |L'aggiunta di un utente tramite un endpoint PSTN  <br/> |
|Utenti client VoIP di Skype for business provenienti da siti di rete diversi  <br/> |Utente client VoIP di Skype for business da qualsiasi sito di rete  <br/> Utente client VoIP di Skype for business da un sito di rete sconosciuto  <br/> Utente client VoIP di Skype for business federativo  <br/> |L'aggiunta di un utente tramite un endpoint PSTN  <br/> |
|Utenti del client VoIP di Skype for business da un singolo sito di rete e utenti che partecipano da un endpoint PSTN  <br/> |Utente client VoIP di Skype for business dello stesso sito di rete  <br/> |Utente client VoIP di Skype for business da un sito di rete diverso  <br/> Utente client VoIP di Skype for business da un sito di rete sconosciuto  <br/> Utente client VoIP di Skype for business federativo  <br/> |

Di seguito sono riportate le caratteristiche aggiuntive del routing basato sulla posizione per le applicazioni di conferenza:

- Quando un utente non è autorizzato a partecipare a una conferenza con restrizioni di routing basate sulla posizione, la chiamata alla conferenza verrà rifiutata e il client Skype for business riferirà che la chiamata non è stata completata o è terminata.

- Un endpoint PSTN che partecipa a una conferenza con le imposte di routing basate sul percorso non sarà limitato per partecipare alla conferenza indipendentemente dallo stato, se l'endpoint si unisce tramite un trunk non abilitato per il routing basato sulla posizione.

- Un sistema PBX connesso a un Mediation Server su un trunk SIP che non esegue l'uscita dalle chiamate alla rete PSTN avrà le stesse imposte degli utenti di Skype for business nello stesso sito di rete in cui è definito il trunk SIP. Ad esempio, un endpoint PSTN sarà in grado di partecipare a una conferenza con un utente PBX e un utente Skype for business se si trovano nello stesso sito di rete; in caso contrario, l'endpoint PSTN non sarà autorizzato a partecipare alla conferenza se l'utente PBX si trova in un sito di rete diverso da quello dell'utente Skype for business.

> [!NOTE]
> Con l'aggiornamento cumulativo 4 di Skype for business, è necessario osservare il comportamento della tabella seguente:

|**Utente**|**Altra parte**|**Azione**|**Risultato**|
|:-----|:-----|:-----|:-----|
|Skype for business per dispositivi mobili  <br/> |PSTN  <br/> |Skype for business mobile è in una chiamata PSTN. Skype for business mobile inoltra la chiamata a un operatore automatico di conferenza (CAA).  <br/> |La chiamata è bloccata e viene visualizzato un messaggio di errore appropriato.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Client Skype for business o utente federato  <br/> |Il client o l'utente federato si trova su una chiamata VoIP a un utente di routing basato sulla posizione di Skype for business per dispositivi mobili e una delle parti viene escalated in CAA.  <br/> |La chiamata a escalation è bloccata e viene visualizzato un messaggio di errore appropriato.  <br/> |

## <a name="consultative-call-transfers"></a>Trasferimenti di chiamate consultive

Oltre a applicare il routing basato sulla posizione alle riunioni di Skype for business, il routing basato sulla posizione per le applicazioni di conferenza impone restrizioni di routing basate sulla posizione per i trasferimenti di chiamate consultive che sono in uscita agli endpoint PSTN. Un trasferimento di chiamata consultiva è una chiamata stabilita tra due parti in cui una delle parti trasferisce la chiamata a un nuovo utente. Ad esempio, un endpoint PSTN chiama l'utente A (chiamato Skype for business). L'utente A determina che l'utente PSTN deve essere inoltrato all'utente B (utente Skype for business). L'utente A inserisce la chiamata con l'utente PSTN in attesa e chiama l'utente B. l'utente B accetta di parlare con l'utente PSTN. L'utente A trasferisce la chiamata in attesa all'utente B.

**Flusso delle chiamate di trasferimento chiamate consultive**

![Diagramma del routing in base alla posizione per le conferenze](../../media/LocationBasedRoutingForConferencing.jpg)

Quando un utente abilitato per il routing basato sulla posizione avvia un trasferimento di chiamata consultiva di un endpoint PSTN (come illustrato nella figura precedente), questo crea due chiamate attive, una chiamata tra l'utente PSTN e l'utente di Skype for business e l'altra tra Skype for Utente aziendale A e utente Skype for business B. il comportamento seguente viene applicato dal routing basato sulla posizione per le applicazioni di conferenza:

- Se il trunk SIP che instrada la chiamata PSTN è autorizzato a reindirizzare la chiamata PSTN al sito di rete in cui si trova l'utente di Skype for business B (cioè destinazione di trasferimento), il trasferimento della chiamata sarà consentito; in caso contrario, il trasferimento delle chiamate consultive verrà bloccato. Questa autorizzazione viene eseguita in base alla posizione dell'entità trasferita che si trova nello stesso sito di rete del trunk SIP che sta instradando la chiamata attiva all'endpoint PSTN.

- Se il trunk SIP che instrada la chiamata PSTN in ingresso non è autorizzato a instradare le chiamate al sito di rete in cui si trova la parte trasferita (utente Skype for business B) o che la parte trasferita si trova in un sito di rete sconosciuto, il trasferimento della chiamata consultiva a l'endpoint PSTN (ad esempio destinazione trasferimento chiamate) verrà bloccato.

La tabella seguente descrive il modo in cui le restrizioni di routing basate sulla posizione vengono applicate dal routing basato sulla posizione per le applicazioni di conferenza per i trasferimenti di chiamate consultive. Anche se gli endpoint PBX non sono associati direttamente a un sito di rete, il trunk SIP a cui è connesso il PBX può essere assegnato a un sito di rete. Di conseguenza, l'endpoint PBX può essere associato indirettamente a un sito di rete.


|**Sito di rete della festa trasferita dalla chiamata**|**Sito di rete della destinazione del trasferimento delle chiamate**|**Comportamento**|
|:-----|:-----|:-----|
|Endpoint PSTN  <br/> |Utenti di Skype for business nello stesso sito di rete (ad esempio, sito 1)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Utenti di Skype for business in siti di rete diversi (ad esempio, sito 2)  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Utenti di Skype for business in un sito di rete sconosciuto  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Utente federato di Skype for business  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Endpoint PBX nello stesso sito (ad esempio il sito 1)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Endpoint PBX in siti diversi (ad esempio, sito 2)  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PBX nello stesso sito (ad esempio il sito 1)  <br/> |Endpoint PSTN  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in un sito diverso (ad esempio, sito 2)  <br/> |Endpoint PSTN  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Utenti di Skype for business nello stesso sito di rete (ad esempio, sito 1)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Utenti di Skype for business in siti di rete diversi (ad esempio, sito 2)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Utenti di Skype for business in un sito di rete sconosciuto  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Utente federato di Skype for business  <br/> |Il trasferimento consultivo sarà consentito  <br/> |

## <a name="requirements"></a>Requisiti

L'applicazione di routing basata sulla posizione per le conferenze richiede che l'aggiornamento cumulativo 2 di Skype for Business Server o Lync Server 2013 sia distribuito in tutti i pool Front-end e nei server standard dell'edizione della topologia. Se queste versioni del server non sono installate in alcuni server della topologia, le restrizioni di routing basate sulla posizione non possono essere applicate completamente alle riunioni e ai trasferimenti delle chiamate consultive.

La tabella seguente identifica la combinazione di ruoli server e versioni che supportano il routing basato sulla posizione.


|**Versione pool Front-End**|**Versione Mediation Server**|**Supportati**|
|:-----|:-----|:-----|
|Aggiornamento cumulativo 2 di Skype for Business Server o Lync Server 2013  <br/> |Aggiornamento cumulativo 2 di Skype for Business Server o Lync Server 2013  <br/> |Sì  <br/> |
|Aggiornamento cumulativo 2 di Lync Server 2013  <br/> |Aggiornamento cumulativo 1 di Lync Server 2013  <br/> |No  <br/> |
|Aggiornamento cumulativo 2 di Lync Server 2013  <br/> |Lync Server 2010  <br/> |No  <br/> |
|Aggiornamento cumulativo 2 di Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |No  <br/> |
|Aggiornamento cumulativo 1 di Lync Server 2013  <br/> |Qualsiasi  <br/> |No  <br/> |
|Lync Server 2010  <br/> |Qualsiasi  <br/> |No  <br/> |
|Office Communications Server 2007 R2  <br/> |Qualsiasi  <br/> |No  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configurazione del routing basato sulla posizione per i servizi di conferenza

L'applicazione di routing basata sulla posizione per le conferenze si basa sulla configurazione del routing basato sulla posizione. Le configurazioni principali sono le seguenti:

- La posizione dei partecipanti che partecipano a una riunione viene determinata in base al sito di rete. Un sito di rete e le subnet di rete associate devono essere definiti in Skype for Business Server per applicare il routing basato sulla posizione.

- Per applicare il routing basato sulla posizione delle riunioni, i partecipanti di Skype for business devono essere abilitati per il routing basato sulla posizione.

- Per applicare il routing basato sulla posizione degli endpoint PSTN che partecipano alle riunioni, il trunk SIP usato per connettere gli endpoint PSTN deve essere configurato per il routing basato sulla posizione.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Abilitazione del routing basato sulla posizione per i servizi di conferenza

L'applicazione di routing basata sulla posizione per le conferenze è disabilitata per impostazione predefinita. Prima di abilitare questa applicazione, devi determinare la priorità giusta da assegnare per l'applicazione. Per determinare questa priorità, eseguire il cmdlet seguente in Skype for Business Server Management Shell:

Get-CsServerApplication-Identity Service: Registrar<Pool FQDN>: in questo cmdlet \<, il\> nome di dominio completo del pool è il pool in cui deve essere abilitata l'applicazione per il routing basato sulla posizione per i servizi di conferenza.

Questo cmdlet restituirà l'elenco delle applicazioni ospitate da Skype for Business Server e il valore di priorità per ognuno di essi. Al routing basato sulla posizione per l'applicazione per i servizi di conferenza deve essere assegnato un valore di priorità maggiore dell'applicazione "UdcAgent" e minore delle applicazioni "DefaultRouting", "ExumRouting" e "OutboundRouting". Ti consigliamo di assegnare il routing basato sulla posizione per l'applicazione per i servizi di conferenza un valore prioritario di un punto superiore al valore di priorità dell'applicazione "UdcAgent".

Ad esempio, se l'applicazione "UdcAgent" ha un valore Priority di "2", l'applicazione "DefaultRouting" ha un valore Priority "8", l'applicazione "ExumRouting" ha un valore Priority di "9" e l'applicazione "OutboundRouting" ha un valore di priorità "10" quindi Devi assegnare il routing basato sulla posizione per l'applicazione per i servizi di conferenza un valore prioritario di "3". In questo modo la priorità delle applicazioni viene applicata nell'ordine seguente: altre applicazioni (priorità: da 0 a 1), "UdcAgent" (priorità: 2), applicazione per i servizi di conferenza di routing basato sulla posizione (priorità: 3), altre applicazioni (priorità: da 4 a 8), " DefaultRouting "(priorità: 9)," ExumRouting "(priorità: 10) e" OutboundRouting "(priorità: 11).

Dopo aver trovato il valore di priorità corretto per l'applicazione di routing basata sulla posizione per i servizi di conferenza, digitare il cmdlet seguente per ogni pool Front-end o server Standard Edition che gli utenti di Homes hanno abilitato per il routing basato sulla posizione:

New-CsServerApplication-Identity Service: Registrar`<Pool FQDN` :>/Lbrouting- \<priorità delle\> applicazioni prioritarie $true-$true Critical-URI<http://www.microsoft.com/LCS/LBRouting> 

Ad esempio:

New-CsServerApplication-Identity Service Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-Urihttp://www.microsoft.com/LCS/LBRouting 

Dopo aver usato questo cmdlet, riavviare tutti i server front-end nel pool o nei server Standard Edition in cui è stata abilitata l'applicazione per il routing basato sulla posizione per i servizi di conferenza.

> [!IMPORTANT]
> Le imposte di routing basate sulla posizione su conferenze o trasferimenti consultivi non verranno applicate fino a quando non vengono riavviati tutti i server front-end nei pool o i server Standard Edition. Se si imposta **-Critical** su **$true** nei cmdlet precedenti, i servizi di Skype for Business Server verranno immediatamente riavviati. Se non si vuole che questi servizi vengano riavviati immediatamente, imposta **-Critical** su **$false** per ora, quindi usare **Set-CsServerApplication** per cambiare il **fattore critico** in **$true** in un secondo momento, dopo che i servizi sono stati riavviati.

Una volta che l'applicazione di routing basata sulla posizione per le conferenze è stata abilitata e tutti i server applicabili sono stati riavviati, tutte le conferenze organizzate dagli utenti di Skype for Business abilitate per il routing basato sulla posizione verranno monitorate per evitare Esclusione di pedaggio PSTN


