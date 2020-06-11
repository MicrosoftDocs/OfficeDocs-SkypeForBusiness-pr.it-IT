---
title: Routing in base alla posizione per le conferenze in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Pianificazione del routing in base alla posizione per le conferenze in Skype for Business Server VoIP aziendale, compresi i trasferimenti di chiamata consultiva.
ms.openlocfilehash: f2a44c1f3275dd0cc9e1205d60ba26e01429ea51
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690582"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Routing in base alla posizione per le conferenze in Skype for Business Server

Pianificazione del routing in base alla posizione per le conferenze in Skype for Business Server VoIP aziendale, compresi i trasferimenti di chiamata consultiva.

Il routing in base alla posizione rende possibile limitare il routing delle chiamate tra endpoint VoIP e endpoint PSTN in base alla posizione delle parti nella chiamata. Il routing in base alla posizione per le conferenze consente di applicare le regole di routing in base alla posizione per le riunioni (ad esempio, conferenze) per impedire il bypass a pedaggio PSTN. L'applicazione monitora una conferenza attiva e applica restrizioni di routing basate sulla posizione in base alla posizione degli utenti che partecipano. L'applicazione per il routing basato sul percorso per le conferenze consente inoltre di applicare restrizioni di routing basate sul percorso ai trasferimenti consultivi che coinvolgono endpoint PSTN.

L'applicazione per le conferenze di routing in base alla posizione fornisce ai congressi Skype for business un meccanismo per la prevenzione del bypass a pedaggio PSTN. L'applicazione monitora le conferenze attive e applica le restrizioni di routing in base alla posizione in base alla posizione degli utenti di Skype for business che partecipano.

L'applicazione per le conferenze di routing basata sulla posizione determina se il routing in base alla posizione deve essere applicato a una riunione di Skype for business, se vengono soddisfatti i seguenti criteri:

- L'organizzatore della riunione è abilitato per il routing in base alla posizione. Le restrizioni di routing in base alla posizione verranno applicate solo alle conferenze organizzate dagli utenti abilitati per il routing basato sulla posizione.

- Almeno un partecipante alla riunione è un endpoint PSTN. Le restrizioni di routing in base alla posizione sono applicabili solo per le conferenze che includono endpoint PSTN.

- Il sito di rete in cui si trova il gateway PSTN utilizzato per colmare la conferenza PSTN e i siti di rete in cui si connettono gli organizzatori e i partecipanti.

L'applicazione per il routing basato sulla posizione per le conferenze impedisce la partecipazione degli utenti di Skype for business e degli endpoint PSTN da siti di rete diversi alla stessa conferenza. Se l'organizzatore di una riunione è abilitato per il routing in base alla posizione, l'applicazione per le conferenze impone le restrizioni seguenti:

- Gli endpoint che possono partecipare a una riunione Skype for business dipendono dagli endpoint che hanno già partecipato alla conferenza e questa restrizione viene modificata in base all'uscita degli endpoint Uniti e ai nuovi endpoint che partecipano alla conferenza. Se gli organizzatori e i partecipanti partecipano a una riunione di Skype for business dallo stesso sito di rete, un endpoint PSTN, un altro partecipante proveniente dallo stesso sito di rete, un altro partecipante proveniente da un sito di rete diverso o da un partecipante di un sito di rete sconosciuto può partecipare.

- Se gli organizzatori e i partecipanti accedono alla riunione da siti di rete diversi o sconosciuti, non è consentito che un endpoint PSTN partecipi alla riunione se la chiamata PSTN accede da un trunk SIP abilitato per il routing in base alla posizione.

- Se gli organizzatori e i partecipanti partecipano alla riunione dallo stesso sito di rete e vi sono partecipanti che partecipano alla stessa riunione dalla rete PSTN, non è consentito partecipare alla riunione con un endpoint di Skype for business proveniente da un altro sito.

Queste restrizioni di routing in base alla posizione per le conferenze sono riepilogate nella tabella seguente.

| |

|**Utente/i in una conferenza in un determinato punto**|**Utenti autorizzati a partecipare alla conferenza**|**Utenti non autorizzati a partecipare alla conferenza**|
|:-----|:-----|:-----|
|Utenti del client VoIP Skype for business da un singolo sito di rete  <br/> |Utente client VoIP Skype for business dallo stesso sito di rete  <br/> Utente client VoIP Skype for business da un sito di rete diverso  <br/> Utente client VoIP Skype for business da un sito di rete sconosciuto  <br/> Utente federato del client VoIP di Skype for business  <br/> Aggiunta di un utente da un endpoint PSTN  <br/> |Nessuno  <br/> |
|Utenti del client VoIP Skype for business da un sito di rete sconosciuto  <br/> |Utente client VoIP Skype for business da qualsiasi sito  <br/> Utente client VoIP Skype for business da un sito sconosciuto  <br/> Utente federato del client VoIP di Skype for business  <br/> |Aggiunta di un utente tramite un endpoint PSTN  <br/> |
|Utenti di client VoIP Skype for business provenienti da siti di rete diversi  <br/> |Utente client VoIP Skype for business da qualsiasi sito di rete  <br/> Utente client VoIP Skype for business da un sito di rete sconosciuto  <br/> Utente federato del client VoIP di Skype for business  <br/> |Aggiunta di un utente tramite un endpoint PSTN  <br/> |
|Utenti del client VoIP Skype for business da un singolo sito di rete e utenti che si congiungono da un endpoint PSTN  <br/> |Utente client VoIP Skype for business dallo stesso sito di rete  <br/> |Utente client VoIP Skype for business da un sito di rete diverso  <br/> Utente client VoIP Skype for business da un sito di rete sconosciuto  <br/> Utente federato del client VoIP di Skype for business  <br/> |

Di seguito sono riportate le caratteristiche aggiuntive del routing basato sulla posizione per l'applicazione per conferenze:

- Quando un utente non è autorizzato a partecipare a una conferenza con restrizioni di routing basate sulla posizione, la chiamata alla conferenza verrà rifiutata e il client Skype for business riporterà che la chiamata non è stata completata o è terminata.

- Un endpoint PSTN che partecipa a una conferenza con l'applicazione del routing in base alla posizione non sarà limitato a partecipare alla conferenza indipendentemente dallo stato, se l'endpoint si unisce tramite un trunk che non è abilitato per il routing basato sulla posizione.

- Un sistema PBX connesso a un Mediation Server tramite un trunk SIP che non effettua l'uscita delle chiamate alla rete PSTN avrà le stesse imposte degli utenti di Skype for business che si trovano nello stesso sito di rete in cui è definito il trunk SIP. Ad esempio, un endpoint PSTN sarà in grado di partecipare a una conferenza con un utente PBX e un utente Skype for business, se si trovano nello stesso sito di rete; in caso contrario, l'endpoint PSTN non sarà autorizzato a partecipare alla conferenza se l'utente PBX si trova in un sito di rete diverso rispetto all'utente Skype for business.

> [!NOTE]
> Con l'aggiornamento cumulativo 4 di Skype for business, è necessario osservare il comportamento nella tabella seguente:

|**Utente**|**Altra parte**|**Azione**|**Risultato**|
|:-----|:-----|:-----|:-----|
|Skype for business per dispositivi mobili  <br/> |PSTN  <br/> |Skype for business mobile è in una chiamata PSTN. Skype for business mobile inoltra la chiamata a un operatore automatico di conferenza (CAA).  <br/> |La chiamata è bloccata, con un messaggio di errore appropriato.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Client Skype for business o utente federato  <br/> |Il client o l'utente federato è su una chiamata VoIP a un utente di routing basato sul percorso di Skype for business mobile e una delle parti viene inoltrata a CAA.  <br/> |La chiamata di escalation è bloccata, con un messaggio di errore appropriato.  <br/> |

## <a name="consultative-call-transfers"></a>Trasferimenti di chiamata consultiva

Oltre a applicare il routing basato sulla posizione alle riunioni di Skype for business, il routing basato sulla posizione per l'applicazione per le conferenze impone restrizioni di routing basate sul percorso nei trasferimenti di chiamata consultiva che vengono esportati negli endpoint PSTN. Un trasferimento di chiamata consultiva è una chiamata stabilita tra due parti in cui una delle parti trasferisce la chiamata a un nuovo utente. Ad esempio, un endpoint PSTN chiama l'utente A (chiamato Skype for business). L'utente A determina che l'utente PSTN deve essere inoltrato all'utente B (Skype for business). Utente A posiziona la chiamata con l'utente PSTN in attesa e chiama l'utente B. User B che accetta di parlare con l'utente PSTN. L'utente A trasferisce la chiamata in attesa all'utente B.

**Flusso delle chiamate di trasferimento delle chiamate consultive**

![Percorso basato sulla posizione per il diagramma delle conferenze](../../media/LocationBasedRoutingForConferencing.jpg)

Quando un utente abilitato per il routing in base alla posizione avvia un trasferimento di chiamata consultivo di un endpoint PSTN (come mostrato nella figura precedente), in questo modo vengono create due chiamate attive, una chiamata tra l'utente PSTN e Skype for Business utente A e l'altra tra gli utenti di Skype for Business utente A e Skype for business B. il comportamento seguente viene applicato dal routing basato sulla posizione per l'applicazione per conferenze :

- Se il trunk SIP che instrada la chiamata PSTN è autorizzato a reindirizzare la chiamata PSTN al sito di rete in cui si trova l'utente Skype for business B (ovvero destinazione trasferimento), il trasferimento di chiamata sarà consentito; in caso contrario, il trasferimento delle chiamate consultive verrà bloccato. Questa autorizzazione viene eseguita in base alla posizione della parte trasferita che si trova nello stesso sito di rete del trunk SIP che esegue il routing della chiamata attiva all'endpoint PSTN.

- Se il trunk SIP che instrada la chiamata PSTN in ingresso non è autorizzato a instradare le chiamate al sito di rete in cui si trova la parte trasferita (utente di Skype for business B) oppure che la parte trasferita si trova in un sito di rete sconosciuto, il trasferimento della chiamata consultiva all'endpoint PSTN (ovvero destinazione trasferimento di chiamata) verrà bloccato.

Nella tabella seguente viene descritto il modo in cui vengono applicate le restrizioni di routing basate sulla posizione per il routing basato sulla posizione per le applicazioni di conferenza per i trasferimenti di chiamata consultiva. Anche se gli endpoint PBX non sono direttamente associati a un sito di rete, il trunk SIP a cui è connesso il sistema PBX può essere assegnato a un sito di rete. Pertanto, l'endpoint PBX può essere associato indirettamente a un sito di rete.


|**Sito di rete di una parte di chiamata trasferita**|**Sito di rete di destinazione trasferimento di chiamata**|**Comportamento**|
|:-----|:-----|:-----|
|Endpoint PSTN  <br/> |Utente di Skype for business nello stesso sito di rete (ad esempio, sito 1)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Utente di Skype for business in diversi siti di rete (ad esempio, sito 2)  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Utente di Skype for business in un sito di rete sconosciuto  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Utente federato di Skype for business  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Endpoint PBX nello stesso sito (ad esempio, sito 1)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Endpoint PBX in siti diversi (ad esempio, sito 2)  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PBX nello stesso sito (ad esempio, sito 1)  <br/> |Endpoint PSTN  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in un sito diverso (ad esempio, sito 2)  <br/> |Endpoint PSTN  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Utente di Skype for business nello stesso sito di rete (ad esempio, sito 1)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Utente di Skype for business in diversi siti di rete (ad esempio, sito 2)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Utente di Skype for business in un sito di rete sconosciuto  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Utente federato di Skype for business  <br/> |Il trasferimento consultivo sarà consentito  <br/> |

## <a name="requirements"></a>Requisiti

L'applicazione per il routing in base alla posizione per le conferenze richiede che Skype for Business Server o Lync Server 2013 Cumulative Update 2 sia distribuito in tutti i pool Front-end e i server Standard Edition nella topologia. Se queste versioni del server non sono installate in alcuni server della topologia, le restrizioni di routing basate sulla posizione non possono essere applicate completamente alle riunioni e ai trasferimenti di chiamata consultiva.

La tabella seguente identifica la combinazione dei ruoli del server e delle versioni che supportano il routing basato sulla posizione.


|**Versione pool Front-End**|**Versione Mediation Server**|**Supportata**|
|:-----|:-----|:-----|
|Aggiornamento cumulativo 2 di Skype for Business Server o Lync Server 2013  <br/> |Aggiornamento cumulativo 2 di Skype for Business Server o Lync Server 2013  <br/> |Sì  <br/> |
|Lync Server 2013 aggiornamento cumulativo 2  <br/> |Lync Server 2013 aggiornamento cumulativo 1  <br/> |No  <br/> |
|Lync Server 2013 aggiornamento cumulativo 2  <br/> |Lync Server 2010  <br/> |No  <br/> |
|Lync Server 2013 aggiornamento cumulativo 2  <br/> |Office Communications Server 2007 R2  <br/> |No  <br/> |
|Lync Server 2013 aggiornamento cumulativo 1  <br/> |Qualsiasi  <br/> |No  <br/> |
|Lync Server 2010  <br/> |Qualsiasi  <br/> |No  <br/> |
|Office Communications Server 2007 R2  <br/> |Qualsiasi  <br/> |No  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configurazione del routing in base alla posizione per le conferenze

Il routing basato sulla posizione per l'applicazione per conferenze si basa sulla configurazione del routing in base alla posizione. Le configurazioni principali sono le seguenti:

- La posizione dei partecipanti che partecipano a una riunione è determinata in base al sito di rete. Un sito di rete e le subnet di rete associate devono essere definite in Skype for Business Server per applicare il routing in base alla posizione.

- Per applicare il routing in base alla posizione delle riunioni, i partecipanti di Skype for business devono essere abilitati per il routing in base alla posizione.

- Per applicare il routing in base alla posizione degli endpoint PSTN che uniscono le riunioni, è necessario configurare il trunk SIP utilizzato per connettere gli endpoint PSTN per il routing basato sulla posizione.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Abilitazione del routing in base alla posizione per le conferenze

Il routing basato sulla posizione per l'applicazione per conferenze è disabilitato per impostazione predefinita. Prima di abilitare questa applicazione, è necessario determinare la priorità giusta da assegnare per l'applicazione. Per determinare questa priorità, eseguire il seguente cmdlet in Skype for Business Server Management Shell:

Get-CsServerApplication-Identity Service: Registrar: <Pool FQDN> in questo cmdlet, \<Pool FQDN\> è il pool in cui deve essere abilitato il routing basato sulla posizione per l'applicazione di conferenza.

Questo cmdlet restituirà l'elenco delle applicazioni ospitate da Skype for Business Server e il valore di priorità per ognuno di essi. All'applicazione di routing in base alla posizione per le conferenze deve essere assegnato un valore di priorità maggiore dell'applicazione "UdcAgent" e più piccolo delle applicazioni "DefaultRouting", "ExumRouting" e "OutboundRouting". Si consiglia di assegnare il routing basato sulla posizione per l'applicazione per le conferenze un valore di priorità che è un punto più alto rispetto al valore di priorità dell'applicazione "UdcAgent".

Ad esempio, se l'applicazione "UdcAgent" ha un valore di priorità pari a "2", l'applicazione "DefaultRouting" ha un valore di priorità pari a "8", l'applicazione "ExumRouting" ha un valore prioritario di "9" e l'applicazione "OutboundRouting" ha un valore di priorità pari a "10", quindi è necessario assegnare il routing basato sulla posizione per l'applicazione di conferenza come valore In questo modo la priorità delle applicazioni verrà eseguita nell'ordine seguente: altre applicazioni (priorità: 0 a 1), "UdcAgent" (priorità: 2), applicazione per le conferenze di routing in base alla posizione (priorità: 3), altre applicazioni (priorità: 4-8), "DefaultRouting" (priorità: 9), "ExumRouting" (priorità: 10) e "OutboundRouting" (priorità: 11).

Dopo aver individuato il valore di priorità corretto per l'applicazione per il routing in base alla posizione per le conferenze, digitare il cmdlet seguente per ogni pool Front-end o server Standard Edition in cui gli utenti di case sono abilitati per il routing basato sulla posizione:

New-CsServerApplication-Identity Service: Registrar: `<Pool FQDN`>/lbrouting-Priority \<Application Priority\> -Enabled $true-Critical $true-Uri<http://www.microsoft.com/LCS/LBRouting>

Ad esempio:

New-CsServerApplication-Identity Service Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-Urihttp://www.microsoft.com/LCS/LBRouting

Dopo aver utilizzato questo cmdlet, riavviare tutti i Front End Server nel pool o nei server Standard Edition in cui è stato abilitato il routing basato sulla posizione per l'applicazione per le conferenze.

> [!IMPORTANT]
> L'applicazione del routing basato sul percorso a conferenze o trasferimenti consultivi non viene applicata finché non vengono riavviati tutti i Front End Server nei pool o nei server Standard Edition. Se si imposta **-Critical** su **$true** nei cmdlet precedenti, i servizi Skype for Business Server verranno riavviati immediatamente. Se non si desidera che questi servizi vengano riavviati immediatamente, impostare **-Critical** su **$false** per il momento e quindi utilizzare **Set-CsServerApplication** per modificare le **condizioni critiche** a **$true** in un secondo momento, dopo che i servizi sono stati riavviati.

Dopo che l'applicazione per il routing basato sulla posizione per le conferenze è stata abilitata e tutti i server applicabili sono stati riavviati, tutte le conferenze organizzate dagli utenti Skype for Business abilitate per il routing in base alla posizione verranno monitorate per impedire il bypass a pedaggio PSTN


