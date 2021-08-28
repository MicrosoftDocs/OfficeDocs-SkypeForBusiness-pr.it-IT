---
title: Location-Based routing per conferenze in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Pianificazione del routing in base alla posizione per le conferenze in Skype for Business Server VoIP aziendale, inclusi i trasferimenti di chiamate consultivi.
ms.openlocfilehash: e5f49dfcc798f4871ff9ecc1ed2fec1beacad8e7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629528"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based routing per conferenze in Skype for Business Server

Pianificazione del routing in base alla posizione per le conferenze in Skype for Business Server VoIP aziendale, inclusi i trasferimenti di chiamate consultivi.

Location-Based routing consente di limitare il routing delle chiamate tra gli endpoint VoIP e gli endpoint PSTN in base alla posizione delle parti nella chiamata. Location-Based routing per conferenze consente di applicare Location-Based regole di routing alle riunioni (ad esempio, le conferenze) per impedire il bypass a pedaggio PSTN. L'applicazione monitora una conferenza attiva e applica Location-Based routing in base alla posizione degli utenti che partecipano. L'Location-Based routing per conferenze consente inoltre l'applicazione delle restrizioni di routing Location-Based ai trasferimenti consultitivi che coinvolgono endpoint PSTN.

L'Location-Based Routing Conferencing fornisce alle conferenze Skype for Business un meccanismo per la prevenzione del bypass a pedaggio PSTN. L'applicazione monitora le conferenze attive e applica Location-Based di routing in base alla posizione degli utenti Skype for Business partecipanti.

LLocation-Based app di routing delle conferenze determina se Location-Based il routing deve essere applicato a una riunione Skype for Business se vengono soddisfatti i criteri seguenti:

- L'organizzatore della riunione è abilitato per Location-Based routing. Location-Based le restrizioni di routing verranno applicate solo alle conferenze organizzate dagli utenti abilitati per Location-Based routing.

- Almeno un partecipante alla riunione è un endpoint PSTN. Location-Based restrizioni di routing sono applicabili solo per le conferenze che includono endpoint PSTN.

- Si trova il sito di rete in cui si trova il gateway PSTN utilizzato per collegare la conferenza alla rete PSTN, nonché i siti di rete da cui si connettono organizzatori e partecipanti.

L'Location-Based routing per conferenze impedisce la partecipazione di Skype for Business utenti ed endpoint PSTN da siti di rete diversi alla stessa conferenza. Se l'organizzatore di una riunione è abilitato Location-Based routing, l'applicazione di conferenza applica le restrizioni seguenti:

- Gli endpoint che possono partecipare a una riunione Skype for Business dipendono dagli endpoint che hanno già partecipato alla conferenza e questa restrizione viene regolata quando gli endpoint aggiunti lasciano e i nuovi endpoint aderiscono alla conferenza. Se organizzatori e partecipanti stanno partecipando a una riunione di Skype for Business dallo stesso sito di rete, un endpoint PSTN, un altro partecipante dello stesso sito di rete, un altro partecipante da un sito di rete diverso o un partecipante da un sito di rete sconosciuto possono partecipare.

- Se organizzatori e partecipanti aderiscono alla riunione da siti di rete diversi o sconosciuti, un endpoint PSTN non può partecipare alla riunione se la chiamata PSTN entra da un trunk SIP abilitato per il routing Location-Based.

- Se gli organizzatori e i partecipanti aderiscono tutti alla riunione dallo stesso sito di rete e vi sono partecipanti che aderiscono alla stessa riunione dalla rete PSTN, un endpoint Skype for Business da un sito di rete diverso non può partecipare alla riunione.

Queste restrizioni Location-Based di routing sono riepilogate nella tabella seguente.

|Utenti in una conferenza in un determinato momento|Utenti autorizzati a partecipare alla conferenza|Utenti non autorizzati a partecipare alla conferenza|
|:-----|:-----|:-----|
|Skype for Business Utenti client VoIP da un singolo sito di rete  <br/> |Skype for Business Utente client VoIP dallo stesso sito di rete  <br/> Skype for Business Utente client VoIP da un sito di rete diverso  <br/> Skype for Business Utente client VoIP da un sito di rete sconosciuto  <br/> Utente client VoIP Skype for Business federato  <br/> Aggiunta di utenti da un endpoint PSTN  <br/> |Nessuno  <br/> |
|Skype for Business Utenti client VoIP da un sito di rete sconosciuto  <br/> |Skype for Business Utente client VoIP da qualsiasi sito  <br/> Skype for Business Utente client VoIP da un sito sconosciuto  <br/> Utente client VoIP Skype for Business federato  <br/> |Aggiunta di utenti tramite un endpoint PSTN  <br/> |
|Skype for Business Utenti client VoIP da siti di rete diversi  <br/> |Skype for Business Utente client VoIP da qualsiasi sito di rete  <br/> Skype for Business Utente client VoIP da un sito di rete sconosciuto  <br/> Utente client VoIP Skype for Business federato  <br/> |Aggiunta di utenti tramite un endpoint PSTN  <br/> |
|Skype for Business Utenti client VoIP da un singolo sito di rete e utenti che a uniscono da un endpoint PSTN  <br/> |Skype for Business Utente client VoIP dallo stesso sito di rete  <br/> |Skype for Business Utente client VoIP da un sito di rete diverso  <br/> Skype for Business Utente client VoIP da un sito di rete sconosciuto  <br/> Utente client VoIP Skype for Business federato  <br/> |

Di seguito sono riportate altre caratteristiche dell'applicazione Location-Based routing per conferenze:

- Quando a un utente non è consentito partecipare Location-Based una conferenza con restrizioni di routing, la chiamata alla conferenza verrà rifiutata e il client Skype for Business segnala che la chiamata non è stata completata o è terminata.

- Un endpoint PSTN che partecipa a una conferenza con Location-Based Le imposizioni del routing non saranno limitate a partecipare alla conferenza indipendentemente dallo stato se l'endpoint si unisce tramite un trunk non abilitato per il routing Location-Based.

- Un sistema PBX connesso a un Mediation Server tramite un trunk SIP che non evade le chiamate alla rete PSTN avrà le stesse imposizioni degli utenti di Skype for Business che si trovano nello stesso sito di rete in cui è definito il trunk SIP. Ad esempio, un endpoint PSTN sarà in grado di partecipare a una conferenza con un utente PBX e un Skype for Business se si trova nello stesso sito di rete. in caso contrario, l'endpoint PSTN non sarà autorizzato a partecipare alla conferenza se l'utente PBX si trova in un sito di rete diverso da quello Skype for Business utente.

> [!NOTE]
> Con Skype for Business cumulativo 4, è necessario osservare il comportamento nella tabella seguente:

|Utente|Other Party|Azione|Risultato|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Il dispositivo mobile è in una chiamata PSTN. Skype for Business Mobile quindi riassalta la chiamata a un Operatore automatico (CAA).  <br/> |La chiamata è bloccata, con un messaggio di errore appropriato.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business Client o utente federato  <br/> |Il client o l'utente federato è in una chiamata VoIP a un utente di routing di Skype for Business Mobile Location-Based ed entrambe le parti vengono inoltrate a un'autorità di certificazione.  <br/> |La chiamata di escalation è bloccata, con un messaggio di errore appropriato.  <br/> |

## <a name="consultative-call-transfers"></a>Trasferimenti di chiamata consultiva

Oltre a applicare il routing Location-Based alle riunioni Skype for Business, l'applicazione Location-Based Routing per conferenze applica restrizioni di routing Location-Based sui trasferimenti di chiamate consultivi in uscita verso gli endpoint PSTN. Un trasferimento di chiamata consultiva è una chiamata stabilita tra due parti in cui una delle parti trasferisce la chiamata a un nuovo utente. Ad esempio, un endpoint PSTN chiama l'utente A (Skype for Business chiamato). L'utente A determina che l'utente PSTN deve essere inoltrato all'utente B (Skype for Business utente). L'utente A mette in attesa la chiamata con l'utente PSTN e chiama l'utente B. L'utente B accetta di parlare con l'utente PSTN. L'utente A trasferisce la chiamata in attesa all'utente B.

**Flusso delle chiamate di trasferimento delle chiamate consultivo**

![Routing in base alla posizione per il diagramma conferenze](../../media/LocationBasedRoutingForConferencing.jpg)

Quando un utente abilitato per il routing di Location-Based avvia un trasferimento di chiamata consultivo di un endpoint PSTN (come illustrato nella figura precedente), vengono create due chiamate attive, una tra l'utente PSTN e l'utente Skype for Business E l'altra tra l'utente Skype for Business E l'utente Skype for Business B. Il comportamento seguente viene applicato dall'applicazione Location-Based Routing per conferenze:

- Se il routing trunk SIP la chiamata PSTN è autorizzata a instradare nuovamente la chiamata PSTN al sito di rete Skype for Business cui si trova l'utente B (ad esempio, destinazione di trasferimento), il trasferimento della chiamata sarà consentito; in caso contrario, il trasferimento di chiamata consultivo verrà bloccato. Questa autorizzazione viene eseguita in base alla posizione della parte trasferita nello stesso sito di rete del trunk SIP che instraderà la chiamata attiva all'endpoint PSTN.

- Se il routing trunk SIP la chiamata PSTN in ingresso non è autorizzata a instradare le chiamate al sito di rete in cui si trova la parte trasferita Skype for Business (utente B) o la parte trasferita si trova in un sito di rete sconosciuto, il trasferimento di chiamata consultivo all'endpoint PSTN (ad esempio, destinazione di trasferimento delle chiamate) verrà bloccato.

Nella tabella seguente viene descritto Location-Based restrizioni di routing applicate dall'applicazione Location-Based routing per conferenze per i trasferimenti di chiamate consultivi. Anche se gli endpoint PBX non sono direttamente associati a un sito di rete, al trunk SIP a cui è connesso il PBX può essere assegnato un sito di rete. Pertanto, l'endpoint PBX può essere associato indirettamente a un sito di rete.


|Sito di rete della parte trasferita|Sito di rete della destinazione di trasferimento delle chiamate|Comportamento|
|:-----|:-----|:-----|
|Endpoint PSTN  <br/> |Skype for Business utente nello stesso sito di rete (ad esempio, sito 1)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Skype for Business utente in siti di rete diversi (ad esempio, sito 2)  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Skype for Business utente in un sito di rete sconosciuto  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Utente Skype for Business federato  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Endpoint PBX nello stesso sito (ad esempio, sito 1)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PSTN  <br/> |Endpoint PBX in un sito diverso (ad esempio, sito 2)  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PBX nello stesso sito (ad esempio, sito 1)  <br/> |Endpoint PSTN  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in un sito diverso (ad esempio, sito 2)  <br/> |Endpoint PSTN  <br/> |Il trasferimento consultivo non sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Skype for Business utente nello stesso sito di rete (ad esempio, sito 1)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Skype for Business utente in siti di rete diversi (ad esempio, sito 2)  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Skype for Business utente in un sito di rete sconosciuto  <br/> |Il trasferimento consultivo sarà consentito  <br/> |
|Endpoint PBX in qualsiasi sito  <br/> |Utente Skype for Business federato  <br/> |Il trasferimento consultivo sarà consentito  <br/> |

## <a name="requirements"></a>Requisiti

L'applicazione Location-Based Routing per conferenze richiede che Skype for Business Server o Lync Server 2013 Cumulative Update 2 sia distribuito in tutti i pool di Front-End e i edizione Standard Server della topologia. Se queste versioni del server non sono installate in alcuni server della topologia, Location-Based le restrizioni di routing non possono essere applicate completamente alle riunioni e ai trasferimenti di chiamate consultiva.

Nella tabella seguente viene identificata la combinazione di ruoli del server e versioni che supportano Location-Based routing.


|Front-End pool|Versione Mediation Server|Supportato|
|:-----|:-----|:-----|
|Skype for Business Server o Aggiornamento cumulativo 2 di Lync Server 2013  <br/> |Skype for Business Server o Aggiornamento cumulativo 2 di Lync Server 2013  <br/> |Sì  <br/> |
|Aggiornamento cumulativo 2 di Lync Server 2013  <br/> |Aggiornamento cumulativo 1 di Lync Server 2013  <br/> |No  <br/> |
|Aggiornamento cumulativo 2 di Lync Server 2013  <br/> |Lync Server 2010  <br/> |No  <br/> |
|Aggiornamento cumulativo 2 di Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |No  <br/> |
|Aggiornamento cumulativo 1 di Lync Server 2013  <br/> |Qualsiasi  <br/> |No  <br/> |
|Lync Server 2010  <br/> |Qualsiasi  <br/> |No  <br/> |
|Office Communications Server 2007 R2  <br/> |Qualsiasi  <br/> |No  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configurazione del routing Location-Based per le conferenze

L'Location-Based routing per conferenze si basa sulla configurazione del routing Location-Based routing. Le configurazioni principali sono le seguenti:

- La posizione dei partecipanti a una riunione viene determinata in base al sito di rete. Un sito di rete e le subnet di rete associate devono essere definiti in Skype for Business Server per applicare Location-Based routing.

- Per applicare Location-Based l'instradamento delle riunioni, Skype for Business i partecipanti devono essere abilitati per Location-Based routing.

- Per applicare Location-Based routing degli endpoint PSTN che a partecipare alle riunioni, il trunk SIP utilizzato per connettere gli endpoint PSTN deve essere configurato per Location-Based routing.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Abilitazione del routing Location-Based per le conferenze

LLocation-Based'applicazione Routing per conferenze è disabilitata per impostazione predefinita. Prima di abilitare questa applicazione, è necessario determinare la priorità giusta da assegnare all'applicazione. Per determinare questa priorità, eseguire il cmdlet seguente in Skype for Business Server Management Shell:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

In questo cmdlet, è il pool in cui deve essere \<Pool FQDN\> Location-Based'applicazione routing per conferenze.

Questo cmdlet restituirà l'elenco delle applicazioni ospitate da Skype for Business Server e il valore di priorità per ognuna di esse. All'applicazione Location-Based Routing per conferenze deve essere assegnato un valore di priorità maggiore dell'applicazione "UdcAgent" e inferiore alle applicazioni "DefaultRouting", "ExumRouting" e "OutboundRouting". È consigliabile assegnare all'applicazione Location-Based routing per conferenze un valore di priorità superiore di un punto rispetto al valore di priorità dell'applicazione "UdcAgent".

Ad esempio, se l'applicazione "UdcAgent" ha un valore di priorità "2", l'applicazione "DefaultRouting" ha un valore di priorità "8", l'applicazione "ExumRouting" ha un valore di priorità "9" e l'applicazione "OutboundRouting" ha un valore di priorità "10", è necessario assegnare all'applicazione Location-Based Routing per conferenze un valore di priorità "3". In questo modo, la priorità delle applicazioni viene posizionata nell'ordine seguente: altre applicazioni (priorità: da 0 a 1), "UdcAgent" (Priorità: 2), Location-Based Routing Conferencing (Priorità: 3), altre applicazioni (priorità: da 4 a 8), "DefaultRouting" (Priorità: 9), "ExumRouting" (Priorità: 10) e "OutboundRouting" (Priorità: 11).

Dopo aver trovato il valore di priorità corretto per l'applicazione Location-Based Routing per conferenze, digitare il cmdlet seguente per ogni pool di Front-End o edizione Standard Server che contiene gli utenti abilitati per il routing Location-Based:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

Ad esempio:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Dopo aver utilizzato questo cmdlet, riavviare tutti i Front End Server del pool o i edizione Standard Server in cui è stata abilitata l'applicazione Location-Based Routing per conferenze.

> [!IMPORTANT]
> Location-Based l'instradamento delle imposizioni alle conferenze o ai trasferimenti di consulenza non verrà applicato fino al riavvio di tutti i Front End Server nei pool applicabili o nei edizione Standard Server. Se si **imposta -Critical** **su $true** nei cmdlet precedenti, i servizi Skype for Business Server verranno riavviati immediatamente. Se non si desidera che questi servizi si riavviino immediatamente, impostare **-Critical** su **$false** per il momento e quindi utilizzare **Set-CsServerApplication** per modificare **-Critical** **in $true in** un secondo momento, dopo il riavvio dei servizi.

Dopo che l'applicazione Location-Based Routing per conferenze è stata abilitata correttamente e tutti i server applicabili sono stati riavviati, tutte le conferenze organizzate dagli utenti di Skype for Business abilitati per il routing Location-Based verranno monitorate per evitare il bypass a pedaggio PSTN


