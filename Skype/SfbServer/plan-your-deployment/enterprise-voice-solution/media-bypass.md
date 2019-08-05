---
title: Pianificare il bypass multimediale in Skype for business
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
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: Decisioni necessarie per la pianificazione del bypass multimediale in Skype for Business Server VoIP aziendale. Include l'interoperabilità con il controllo di ammissione delle chiamate (CAC).
ms.openlocfilehash: 9db3d9aec6af0cccec951faa3b103d7660a6944b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187628"
---
# <a name="plan-for-media-bypass-in-skype-for-business"></a>Pianificare il bypass multimediale in Skype for business

Decisioni necessarie per la pianificazione del bypass multimediale in Skype for Business Server VoIP aziendale. Include l'interoperabilità con il controllo di ammissione delle chiamate (CAC).

Il bypass multimediale si riferisce alla rimozione del Mediation Server dal percorso multimediale ogni volta che è possibile per le chiamate il cui segnale attraversa il Mediation Server.

Il bypass multimediale può migliorare la qualità della voce riducendo la latenza, la traduzione inutile, la possibilità di perdita di pacchetti e il numero di punti di potenziale errore. La scalabilità può essere migliorata perché l'eliminazione dell'elaborazione multimediale per le chiamate bypassate riduce il carico sul server Mediation. Questa riduzione del carico complementa la capacità del server Mediation di controllare più gateway.

 Se un sito di succursale senza un Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda vincolata, il bypass multimediale abbassa il requisito della larghezza di banda consentendo agli elementi multimediali di un client in un sito di succursale di scorrere direttamente nel gateway locale senza prima di tutto è necessario scorrere il collegamento WAN a un Mediation Server nel sito centrale e viceversa.

Attenuando il Mediation Server dall'elaborazione multimediale, il bypass multimediale può anche ridurre il numero di server di mediazione necessari per l'infrastruttura VoIP aziendale. Come regola generale, abilitare il bypass multimediale ovunque sia possibile.

Nella figura seguente vengono illustrati i percorsi multimediali e di segnalazione di base nelle topologie con e senza bypass multimediale.

**Percorsi multimediali e di segnalazione con e senza bypass multimediale**

![Applicazione del controllo di ammissione di chiamata vocale con bypass multimediale sulle connessioni](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

Il bypass multimediale è utile quando si vuole ridurre al minimo il numero di server di mediazione distribuiti. In genere, un pool di Mediation Server verrà distribuito in un sito centrale e controllerà i gateway nei siti di succursale. L'abilitazione del bypass multimediale consente alle chiamate PSTN (Public Switched Telephone Network) dei client in siti di succursale di scorrere direttamente attraverso i gateway in questi siti. Le route delle chiamate in uscita e i criteri VoIP aziendale di Skype for Business Server devono essere configurati correttamente in modo che le chiamate PSTN da client in un sito di succursale vengano indirizzate al gateway appropriato.

Le reti Wi-Fi in genere avvertono più perdita di pacchetti rispetto alle reti cablate. Il ripristino da questa perdita di pacchetti non è in genere un elemento che può essere ospitato da gateway. Per questo motivo, ti consigliamo di valutare la qualità di una rete Wi-Fi prima di determinare se l'esclusione deve essere abilitata per una subnet wireless. C'è un compromesso nella riduzione della latenza rispetto al recupero dalla perdita di pacchetti da considerare anche. RTAudio, un codec disponibile per le chiamate che non ignorano il Mediation Server, è più adatto per la gestione della perdita di pacchetti.

## <a name="planning-your-media-bypass-deployment"></a>Pianificazione della distribuzione di bypass multimediale

Una volta posizionata la struttura VoIP aziendale, la pianificazione per il bypass multimediale è semplice.

- Se si ha una topologia centralizzata senza collegamenti WAN a siti di succursale, è possibile abilitare il bypass multimediale globale, perché il controllo ottimizzato non è necessario.

- Se si dispone di una topologia distribuita costituita da una o più aree di rete e dai siti di filiale affiliati, determinare le operazioni seguenti:

  - Se i peer di Mediation Server sono in grado di supportare le funzionalità necessarie per il bypass multimediale.

  - I siti di ogni area di rete sono ben connessi.

  - Quale combinazione di bypass multimediale e controllo di ammissione di chiamata è appropriata per la rete.

Quando si Abilita il bypass multimediale, viene generato automaticamente un ID di bypass univoco per un'area di rete e per tutti i siti di rete senza vincoli di larghezza di banda all'interno dell'area geografica. I siti con vincoli di larghezza di banda nell'area geografica e i siti connessi all'area geografica con collegamenti WAN con vincoli di larghezza di banda sono assegnati ad ognuno un ID di bypass univoco.

Quando un utente effettua una chiamata alla rete PSTN, il Mediation Server confronta l'ID di bypass della subnet client con l'ID di bypass della subnet del gateway. Se i due ID di bypass corrispondono, per la chiamata viene usato il bypass multimediale. Se gli ID di bypass non corrispondono, il supporto per la chiamata deve fluire attraverso il Mediation Server.

Quando un utente riceve una chiamata dalla rete PSTN, il client dell'utente confronta il proprio ID di esclusione con quello del gateway PSTN. Se i due ID di bypass corrispondono, il flusso multimediale passa direttamente dal gateway al client, bypassando il Mediation Server.

Solo Lync 2010 o i client e i dispositivi più recenti supportano le interazioni di bypass multimediale con un Mediation Server.

> [!IMPORTANT]
> Oltre a consentire il bypass multimediale a livello globale, è necessario abilitare individualmente il bypass multimediale in ogni trunk PSTN. Se il bypass è abilitato globalmente, ma non è abilitato per un trunk PSTN specifico, il bypass multimediale non verrà richiamato per le chiamate che coinvolgono il trunk PSTN. Inoltre, quando il bypass multimediale è impostato per l' **uso di informazioni sul sito e sull'area geografica**, è necessario associare tutte le subnet instradabili ai siti in cui si trovano. Se sono presenti subnet instradabili all'interno di un sito per cui il bypass non è desiderato, queste subnet devono essere raggruppate all'interno di un nuovo sito prima di abilitare il bypass multimediale. In questo modo si assicurerà che alle subnet non instradabili sia assegnato un ID di bypass diverso.

## <a name="media-bypass-modes"></a>Modalità di bypass multimediale

È necessario configurare il bypass multimediale sia a livello globale che per ogni singolo trunk PSTN. Quando si Abilita il bypass multimediale a livello globale, sono disponibili due opzioni: **Ignora sempre** e **Usa le informazioni sul sito e le aree**geografiche.

Come suggerisce il nome, il **bypass indica sempre** che il bypass verrà tentato per tutte le chiamate PSTN. Il bypass viene usato **sempre** per le distribuzioni in cui non è necessario abilitare il controllo di ammissione alle chiamate e non è necessario specificare informazioni dettagliate sulla configurazione per il tentativo di bypass multimediale. Inoltre, **sempre l'esclusione** viene usata quando esiste una connettività completa tra client e gateway PSTN. In questa configurazione tutte le subnet sono mappate a uno e solo un ID di bypass, calcolato dal sistema.

Con le **informazioni sull'uso di siti e aree**geografiche, l'ID di bypass associato alla configurazione del sito e dell'area geografica viene usato per prendere la decisione di bypass. Questa configurazione offre la flessibilità necessaria per configurare il bypass per le topologie più comuni, in quanto offre un controllo preciso quando si verifica un bypass, oltre a supportare le interazioni con il controllo di ammissione alle chiamate (CAC). Il sistema cerca di semplificare l'attività assegnando automaticamente gli ID di bypass come indicato di seguito.

- Il sistema assegna automaticamente un singolo ID di bypass univoco a ogni area geografica.

- Qualsiasi sito connesso a un'area geografica su un collegamento WAN senza vincoli di larghezza di banda eredita lo stesso ID di bypass dell'area geografica.

- Un sito associato all'area geografica su un collegamento WAN con larghezza di banda vincolata viene assegnato un ID di bypass diverso da quello dell'area geografica.

- Le subnet associate a ogni sito ereditano l'ID di bypass per il sito.

## <a name="media-bypass-and-call-admission-control"></a>Bypass multimediale e controllo di ammissione di chiamata

Bypass multimediale e controllo di ammissione alle chiamate (CAC) collaborare per gestire il controllo della larghezza di banda per il supporto delle chiamate. Il bypass multimediale facilita il flusso multimediale sui collegamenti collegati correttamente; CAC gestisce il traffico sui collegamenti con vincoli di larghezza di banda. Poiché il bypass multimediale e il CAC si escludono a vicenda, è necessario essere consapevoli di uno durante la pianificazione per l'altro. Sono supportate le combinazioni seguenti:

- CAC e bypass multimediale sono entrambi abilitati. Il bypass multimediale deve essere impostato per l' **uso di informazioni sul sito e sulle aree**geografiche. Le informazioni di questo sito e area geografica sono le stesse usate per CAC.

    Se si Abilita CAC, non è possibile selezionare **sempre l'esclusione**e viceversa, perché le due configurazioni si escludono a vicenda. Vale a dire che solo uno dei due verrà applicato a qualsiasi chiamata PSTN specificata. Viene innanzitutto eseguito un controllo per determinare se il bypass multimediale si applica alla chiamata. In caso affermativo, il CAC non viene usato. Questo ha senso, perché se una chiamata è idonea per il bypass, è per definizione usando una connessione in cui CAC non è necessario. Se non è possibile applicare l'esclusione alla chiamata, ovvero se gli ID di bypass del client e del gateway non corrispondono, viene applicato il CAC alla chiamata.

- CAC non abilitato e il bypass multimediale impostato su **Ignora sempre**.

    In questa configurazione, sia le subnet client che quelle trunk sono mappate a uno e solo un ID di bypass, calcolato dal sistema.

- CAC non abilitato e bypass multimediale impostato per l' **uso di informazioni sul sito e sulle aree**geografiche.

    Dove è abilitata l' **uso delle informazioni sul sito e sull'area geografica** , la determinazione di bypass funziona essenzialmente allo stesso modo, indipendentemente dal fatto che CAC sia abilitato. Per qualsiasi chiamata PSTN, la subnet del client viene mappata a un determinato sito e viene estratto l'ID di bypass per la subnet. Analogamente, la subnet del gateway viene mappata a un determinato sito e viene estratto l'ID di bypass per la subnet. Solo se i due ID di bypass sono identici verranno ignorati per la chiamata. Se non sono identici, il bypass multimediale non si verificherà.

    Anche se CAC è disabilitato a livello globale, è necessario definire i criteri di larghezza di banda per ogni sito e collegamento se si vuole usare la configurazione del sito e dell'area geografica per controllare la decisione di esclusione. Il valore effettivo del vincolo di larghezza di banda o della relativa modalità non ha importanza. L'obiettivo finale è quello di far calcolare automaticamente i diversi ID di bypass da associare a impostazioni locali diverse che non sono ben connesse. La definizione di un vincolo di larghezza di banda per definizione significa che un collegamento non è ben connesso.

- CAC è abilitato e il bypass multimediale non è abilitato. Questo problema si applica solo quando tutti i gateway e i PBX IP non sono ben connessi o non soddisfano altri requisiti per il bypass multimediale. Per informazioni dettagliate sui requisiti per il bypass multimediale, vedere [requisiti per il bypass multimediale](https://technet.microsoft.com/library/6162a204-0e7c-460a-8eb2-e592c6590a8a.aspx).

## <a name="technical-requirements"></a>Requisiti tecnici

Per ogni chiamata alla rete PSTN, Mediation Server determina se l'elemento multimediale dell'endpoint di Skype for business di origine può essere inviato direttamente a un peer di Mediation Server senza attraversare il Mediation Server. Il peer può essere un gateway PSTN, un IP-PBX o un SBC (Session Border Controller) in un provider di servizi di telefonia Internet (ITSP) associato al trunk tra il Mediation Server in cui viene instradata la chiamata.

Il bypass multimediale può essere impiegato quando si soddisfano i requisiti seguenti:

- Un peer di Mediation Server deve supportare le funzionalità necessarie per il bypass multimediale, la più importante è la possibilità di gestire più risposte a forcella (dette "finestre di dialogo iniziali"). Contattare il produttore del gateway o del PBX o del proprio ITSP per ottenere il valore per il numero massimo di finestre di dialogo iniziali che il gateway, il PBX o il SBC può accettare.

- Il peer Mediation Server deve accettare il traffico multimediale direttamente dagli endpoint di Skype for business. Molti ITSPs consentono a SBC di ricevere traffico solo dal Mediation Server. Contattare il proprio ITSP per determinare se il proprio SBC accetta il traffico multimediale direttamente dagli endpoint di Skype for business.

- I client Skype for business e un peer di Mediation Server devono essere ben connessi, quindi si trovano nella stessa area di rete o nei siti di rete che si connettono all'area geografica con collegamenti WAN senza vincoli di larghezza di banda


