---
title: Location-Based routing per le conferenze in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 744f4b313f7ea458013aa0e45cff37ebbf85068a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825576"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based routing per le conferenze in Skype for Business Server

Pianificazione del routing in base alla posizione per le conferenze in Skype for Business Server VoIP aziendale, compresi i trasferimenti di chiamata consultiva.

Location-Based routing rende possibile limitare il routing delle chiamate tra endpoint VoIP e endpoint PSTN in base alla posizione delle parti nella chiamata. Location-Based routing per le conferenze consente di applicare Location-Based regole di routing per le riunioni (ad esempio, conferenze) per impedire il bypass a pedaggio PSTN. L'applicazione monitora una conferenza attiva e applica Location-Based limitazioni del routing in base alla posizione degli utenti che partecipano. L'applicazione di routing Location-Based per le conferenze consente inoltre di applicare le restrizioni di routing Location-Based ai trasferimenti consultivi che coinvolgono endpoint PSTN.

L'applicazione di routing per le conferenze di Location-Based fornisce ai congressi Skype for business un meccanismo per la prevenzione del bypass a pedaggio PSTN. L'applicazione monitora le conferenze attive e applica Location-Based limitazioni di routing in base alla posizione degli utenti di Skype for business che partecipano.

L'applicazione Location-Based routing Conferencing determina se Location-Based il routing deve essere applicato a una riunione di Skype for business, se vengono soddisfatti i seguenti criteri:

- L'organizzatore della riunione è abilitato per il routing Location-Based. Le restrizioni di routing Location-Based verranno applicate solo alle conferenze organizzate dagli utenti abilitati per il routing Location-Based.

- Almeno un partecipante alla riunione è un endpoint PSTN. Location-Based le restrizioni di routing sono applicabili solo per le conferenze che includono endpoint PSTN.

- Il sito di rete in cui si trova il gateway PSTN utilizzato per colmare la conferenza PSTN e i siti di rete in cui si connettono gli organizzatori e i partecipanti.

L'applicazione di routing Location-Based per le conferenze impedisce la partecipazione degli utenti di Skype for business e degli endpoint PSTN provenienti da siti di rete diversi alla stessa conferenza. Se l'organizzatore di una riunione è abilitato per il routing Location-Based, l'applicazione per conferenze impone le restrizioni seguenti:

- Gli endpoint che possono partecipare a una riunione Skype for business dipendono dagli endpoint che hanno già partecipato alla conferenza e questa restrizione viene modificata in base all'uscita degli endpoint Uniti e ai nuovi endpoint che partecipano alla conferenza. Se gli organizzatori e i partecipanti partecipano a una riunione di Skype for business dallo stesso sito di rete, un endpoint PSTN, un altro partecipante proveniente dallo stesso sito di rete, un altro partecipante proveniente da un sito di rete diverso o da un partecipante di un sito di rete sconosciuto può partecipare.

- Se gli organizzatori e i partecipanti accedono alla riunione da siti di rete diversi o sconosciuti, non è consentito che un endpoint PSTN partecipi alla riunione se la chiamata PSTN accede da un trunk SIP abilitato per il routing Location-Based.

- Se gli organizzatori e i partecipanti partecipano alla riunione dallo stesso sito di rete e vi sono partecipanti che partecipano alla stessa riunione dalla rete PSTN, non è consentito partecipare alla riunione con un endpoint di Skype for business proveniente da un altro sito.

Queste restrizioni di routing Location-Based di conferenza sono riepilogate nella tabella seguente.

|Utente/i in una conferenza in un determinato punto|Utenti autorizzati a partecipare alla conferenza|Utenti non autorizzati a partecipare alla conferenza|
|:-----|:-----|:-----|
|Utenti del client VoIP Skype for business da un singolo sito di rete  <br/> |Utente client VoIP Skype for business dallo stesso sito di rete  <br/> Utente client VoIP Skype for business da un sito di rete diverso  <br/> Utente client VoIP Skype for business da un sito di rete sconosciuto  <br/> Utente federato del client VoIP di Skype for business  <br/> Aggiunta di un utente da un endpoint PSTN  <br/> |Nessuno  <br/> |
|Utenti del client VoIP Skype for business da un sito di rete sconosciuto  <br/> |Utente client VoIP Skype for business da qualsiasi sito  <br/> Utente client VoIP Skype for business da un sito sconosciuto  <br/> Utente federato del client VoIP di Skype for business  <br/> |Aggiunta di un utente tramite un endpoint PSTN  <br/> |
|Utenti di client VoIP Skype for business provenienti da siti di rete diversi  <br/> |Utente client VoIP Skype for business da qualsiasi sito di rete  <br/> Utente client VoIP Skype for business da un sito di rete sconosciuto  <br/> Utente federato del client VoIP di Skype for business  <br/> |Aggiunta di un utente tramite un endpoint PSTN  <br/> |
|Utenti del client VoIP Skype for business da un singolo sito di rete e utenti che si congiungono da un endpoint PSTN  <br/> |Utente client VoIP Skype for business dallo stesso sito di rete  <br/> |Utente client VoIP Skype for business da un sito di rete diverso  <br/> Utente client VoIP Skype for business da un sito di rete sconosciuto  <br/> Utente federato del client VoIP di Skype for business  <br/> |

Di seguito sono riportate le caratteristiche aggiuntive dell'applicazione di routing Location-Based per le conferenze:

- Quando un utente non è autorizzato a partecipare a una conferenza con Location-Based limitazioni del routing, la chiamata alla conferenza verrà rifiutata e il client Skype for business riporterà che la chiamata non è stata completata o è terminata.

- Un endpoint PSTN che partecipa a una conferenza con Location-Based le imposte del routing non sarà limitato a partecipare alla conferenza indipendentemente dal relativo stato, se l'endpoint si unisce tramite un trunk che non è abilitato per il routing Location-Based.

- Un sistema PBX connesso a un Mediation Server tramite un trunk SIP che non effettua l'uscita delle chiamate alla rete PSTN avrà le stesse imposte degli utenti di Skype for business che si trovano nello stesso sito di rete in cui è definito il trunk SIP. Ad esempio, un endpoint PSTN sarà in grado di partecipare a una conferenza con un utente PBX e un utente Skype for business, se si trovano nello stesso sito di rete; in caso contrario, l'endpoint PSTN non sarà autorizzato a partecipare alla conferenza se l'utente PBX si trova in un sito di rete diverso rispetto all'utente Skype for business.

> [!NOTE]
> Con l'aggiornamento cumulativo 4 di Skype for business, è necessario osservare il comportamento nella tabella seguente:

|Utente|Altra parte|Azione|Risultato|
|:-----|:-----|:-----|:-----|
|Skype for business per dispositivi mobili  <br/> |PSTN  <br/> |Skype for business mobile è in una chiamata PSTN. Skype for business mobile inoltra la chiamata a un operatore automatico di conferenza (CAA).  <br/> |La chiamata è bloccata, con un messaggio di errore appropriato.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Client Skype for business o utente federato  <br/> |Il client o l'utente federato è su una chiamata VoIP a un utente di routing Location-Based per dispositivi mobili di Skype for business e l'altra parte viene inoltrata a CAA.  <br/> |La chiamata di escalation è bloccata, con un messaggio di errore appropriato.  <br/> |

## <a name="consultative-call-transfers"></a>Trasferimenti di chiamata consultiva

Oltre a applicare il routing Location-Based alle riunioni di Skype for business, il Location-Based routing per le applicazioni di conferenza impone Location-Based limitazioni di routing per i trasferimenti di chiamata consultiva che vengono esportati negli endpoint PSTN. Un trasferimento di chiamata consultiva è una chiamata stabilita tra due parti in cui una delle parti trasferisce la chiamata a un nuovo utente. Ad esempio, un endpoint PSTN chiama l'utente A (chiamato Skype for business). L'utente A determina che l'utente PSTN deve essere inoltrato all'utente B (Skype for business). Utente A posiziona la chiamata con l'utente PSTN in attesa e chiama l'utente B. User B che accetta di parlare con l'utente PSTN. L'utente A trasferisce la chiamata in attesa all'utente B.

**Flusso delle chiamate di trasferimento delle chiamate consultive**

![Percorso basato sulla posizione per il diagramma delle conferenze](../../media/LocationBasedRoutingForConferencing.jpg)

Quando un utente abilitato per il routing Location-Based avvia un trasferimento di chiamata consultivo di un endpoint PSTN (come mostrato nella figura precedente), vengono create due chiamate attive, una chiamata tra l'utente PSTN e Skype for Business utente A e l'altra tra Skype for Business utente A e Skype for Business utente B. il comportamento seguente viene applicato dall'Location-Based routing per l'applicazione per le conferenze:

- Se il trunk SIP che instrada la chiamata PSTN è autorizzato a reindirizzare la chiamata PSTN al sito di rete in cui si trova l'utente Skype for business B (ovvero, destinazione trasferimento), il trasferimento di chiamata sarà consentito; in caso contrario, il trasferimento delle chiamate consultive verrà bloccato. Questa autorizzazione viene eseguita in base alla posizione della parte trasferita che si trova nello stesso sito di rete del trunk SIP che esegue il routing della chiamata attiva all'endpoint PSTN.

- Se il trunk SIP che instrada la chiamata PSTN in ingresso non è autorizzato a instradare le chiamate al sito di rete in cui si trova la parte trasferita (utente di Skype for business B) oppure che la parte trasferita si trova in un sito di rete sconosciuto, il trasferimento della chiamata consultiva all'endpoint PSTN (ovvero l'obiettivo di trasferimento di chiamata) verrà bloccato.

Nella tabella seguente viene descritto in che modo Location-Based le restrizioni di routing vengono applicate dall'Location-Based routing per l'applicazione per conferenze per i trasferimenti di chiamata consultiva. Anche se gli endpoint PBX non sono direttamente associati a un sito di rete, il trunk SIP a cui è connesso il sistema PBX può essere assegnato a un sito di rete. Pertanto, l'endpoint PBX può essere associato indirettamente a un sito di rete.


|Sito di rete di una parte di chiamata trasferita|Sito di rete di destinazione trasferimento di chiamata|Comportamento|
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

L'applicazione di routing Location-Based per i servizi di conferenza richiede che Skype for Business Server o Lync Server 2013 Cumulative Update 2 sia distribuito su tutti i pool di Front-End e server Standard Edition nella topologia. Se queste versioni del server non sono installate in alcuni server della topologia, Location-Based restrizioni di routing non possono essere applicate completamente alle riunioni e ai trasferimenti di chiamata consultiva.

La tabella seguente identifica la combinazione di ruoli del server e versioni che supportano il routing Location-Based.


|Versione del pool di Front-End|Versione Mediation Server|Supportato|
|:-----|:-----|:-----|
|Aggiornamento cumulativo 2 di Skype for Business Server o Lync Server 2013  <br/> |Aggiornamento cumulativo 2 di Skype for Business Server o Lync Server 2013  <br/> |Sì  <br/> |
|Lync Server 2013 aggiornamento cumulativo 2  <br/> |Lync Server 2013 aggiornamento cumulativo 1  <br/> |No  <br/> |
|Lync Server 2013 aggiornamento cumulativo 2  <br/> |Lync Server 2010  <br/> |No  <br/> |
|Lync Server 2013 aggiornamento cumulativo 2  <br/> |Office Communications Server 2007 R2  <br/> |No  <br/> |
|Lync Server 2013 aggiornamento cumulativo 1  <br/> |Qualsiasi  <br/> |No  <br/> |
|Lync Server 2010  <br/> |Qualsiasi  <br/> |No  <br/> |
|Office Communications Server 2007 R2  <br/> |Qualsiasi  <br/> |No  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configurazione del routing Location-Based per le conferenze

L'applicazione di routing Location-Based per le conferenze si basa sulla configurazione del routing Location-Based. Le configurazioni principali sono le seguenti:

- La posizione dei partecipanti che partecipano a una riunione è determinata in base al sito di rete. Un sito di rete e le subnet di rete associate devono essere definiti in Skype for Business Server per applicare il routing Location-Based.

- Per applicare Location-Based routing delle riunioni, i partecipanti di Skype for business devono essere abilitati per il routing Location-Based.

- Per applicare il routing Location-Based degli endpoint PSTN che uniscono le riunioni, è necessario configurare il trunk SIP utilizzato per connettere gli endpoint PSTN per il routing Location-Based.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Abilitazione del routing Location-Based per le conferenze

L'applicazione di routing Location-Based per le conferenze è disabilitata per impostazione predefinita. Prima di abilitare questa applicazione, è necessario determinare la priorità giusta da assegnare per l'applicazione. Per determinare questa priorità, eseguire il seguente cmdlet in Skype for Business Server Management Shell:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

In questo cmdlet, \<Pool FQDN\> è il pool in cui deve essere abilitata l'applicazione di routing per l'Location-Based per le conferenze.

Questo cmdlet restituirà l'elenco delle applicazioni ospitate da Skype for Business Server e il valore di priorità per ognuno di essi. All'applicazione di routing Location-Based per le conferenze deve essere assegnato un valore di priorità maggiore dell'applicazione "UdcAgent" e più piccolo delle applicazioni "DefaultRouting", "ExumRouting" e "OutboundRouting". Si consiglia di assegnare il routing Location-Based per l'applicazione per le conferenze un valore di priorità che è un punto più alto rispetto al valore di priorità dell'applicazione "UdcAgent".

Ad esempio, se l'applicazione "UdcAgent" ha un valore di priorità pari a "2", l'applicazione "DefaultRouting" ha un valore di priorità "8", l'applicazione "ExumRouting" ha un valore prioritario di "9" e l'applicazione "OutboundRouting" ha un valore di priorità pari a "10", quindi è necessario assegnare il Location-Based routing per le applicazioni di conferenza un valore di In questo modo la priorità delle applicazioni verrà eseguita nell'ordine seguente: altre applicazioni (priorità: 0 a 1), "UdcAgent" (priorità: 2), Location-Based applicazione per le conferenze di routing (priorità: 3), altre applicazioni (priorità: 4 a 8), "DefaultRouting" (priorità: 9), "ExumRouting" (priorità: 10) e "OutboundRouting" (priorità: 11).

Dopo aver individuato il valore di priorità corretto per l'applicazione di routing Location-Based per le conferenze, digitare il seguente cmdlet per ogni pool di Front-End o server Standard Edition in cui gli utenti di case sono abilitati per il routing Location-Based:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

Ad esempio:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Dopo aver utilizzato questo cmdlet, riavviare tutti i Front End Server nel pool o nei server Standard Edition in cui è stata abilitata l'applicazione di routing Location-Based per le conferenze.

> [!IMPORTANT]
> Location-Based l'applicazione di routing alle conferenze o ai trasferimenti consultivi non verrà applicata finché non vengono riavviati tutti i Front End Server nei pool o nei server Standard Edition. Se si imposta **-Critical** su **$true** nei cmdlet precedenti, i servizi Skype for Business Server verranno riavviati immediatamente. Se non si desidera che questi servizi vengano riavviati immediatamente, impostare **-Critical** su **$false** per il momento e quindi utilizzare **Set-CsServerApplication** per modificare le **condizioni critiche** a **$true** in un secondo momento, dopo che i servizi sono stati riavviati.

Una volta abilitata la Location-Based routing per l'applicazione per le conferenze e tutti i server applicabili sono stati riavviati, vengono monitorate tutte le conferenze organizzate dagli utenti di Skype for Business abilitate per Location-Based il routing per impedire il bypass a pedaggio PSTN


