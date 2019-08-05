---
title: Contatori delle prestazioni di mobilità in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Riepilogo: informazioni sui contatori delle prestazioni che è possibile usare per monitorare i server che usano Unified Communications Web API (UCWA) e il servizio di mobilità MCX di Skype for Business Server.'
ms.openlocfilehash: 91ca77b9719dc6b76ea9bb054856abf82bb3ebd4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188729"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Contatori delle prestazioni di mobilità in Skype for Business Server
 
**Riepilogo:** Informazioni sui contatori delle prestazioni che è possibile usare per monitorare i server che usano Unified Communications Web API (UCWA) e il servizio di mobilità MCX di Skype for Business Server.
  
Le tabelle seguenti elencano i nomi e le descrizioni dei contatori delle prestazioni che è possibile usare per monitorare i server che usano Unified Communications Web API (UCWA) e il servizio di mobilità MCX di Skype for Business Server. 
  
Il nome della categoria per i contatori nella tabella UCWA è **ls: Web-UCWA**.
  
Il nome della categoria per i contatori nella tabella del servizio di mobilità MCX è **ls: Web-servizio di comunicazione mobile**.

> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="performance-counters-for-ucwa"></a>Contatori delle prestazioni per UCWA

|Contatore|Descrizione|
|:-----|:-----|
|Conteggio applicazioni attive  <br/> |Numero corrente di applicazioni  <br/> |
|Conteggio delle modalità di condivisione delle applicazioni attive  <br/> |Numero corrente di modalità di condivisione delle applicazioni  <br/> |
|Conteggio modalità audio attiva  <br/> |Numero corrente di modalità audio  <br/> |
|Conteggio delle modalità di collaborazione con i dati attivi  <br/> |Numero corrente di modalità di collaborazione dei dati  <br/> |
|Active Directory Photo Get latenza (MS)  <br/> |Questo contatore mostra il tempo medio (in millisecondi) per recuperare una foto da Active Directory  <br/> |
|Conteggio delle modalità di messaggistica attiva  <br/> |Numero corrente di modalità di messaggistica  <br/> |
|Conteggio delle modalità video panoramico attivo  <br/> |Numero corrente di modalità video panoramico  <br/> |
|Conteggio in sospeso attivo  <br/> |Il numero di ritorni in sospeso attualmente attivi; connessioni Long-Held al server  <br/> |
|Conteggio sessioni attive  <br/> |Numero corrente di endpoint registrati in UCWA per applicazione e totale  <br/> |
|Conteggio istanze utente attivo  <br/> |Numero corrente di istanze utente  <br/> |
|Istanze utente attive senza applicazione  <br/> |Numero corrente di istanze utente senza applicazione  <br/> |
|Conteggio modalità video attivo  <br/> |Numero corrente di modalità video  <br/> |
|Richieste di creazione di applicazioni ricevute/seconde  <br/> |Tasso per secondo delle richieste di creazione di applicazioni ricevute  <br/> |
|Errori di join di MCU  <br/> |Numero di errori di join di MCU  <br/> |
|Errore di join di MCU AV  <br/> |Numero di errori di join di MCU AV  <br/> |
|Tempo di avvio dell'applicazione medio (MS)  <br/> |Tempo di avvio dell'applicazione medio in millisecondi  <br/> |
|Durata media per la sessione (MS)  <br/> |Durata media per una sessione in millisecondi  <br/> |
|Errori di join di MCU dati  <br/> |Numero di errori di join di MCU dati  <br/> |
|Latenza ricerca contatti di Exchange (MS)  <br/> |Questo contatore mostra il tempo medio (in millisecondi) per cercare il contatto in Exchange  <br/> |
|Exchange HD Photo Get latenza (MS)  <br/> |Questo contatore mostra il tempo medio (in millisecondi) per recuperare una foto da Exchange  <br/> |
|Risposte 4xx HTTP/secondo  <br/> |Il tasso di risposta al secondo con il codice HTTP 4xx  <br/> |
|Risposte 5xx HTTP/secondo  <br/> |Il tasso di risposta al secondo con il codice HTTP 5xx  <br/> |
|Errori di join di MCU di messaggistica istantanea  <br/> |Numero di errori di join di MCU di messaggistica istantanea  <br/> |
|Numero di foto di Active Directory Get Failures  <br/> |Numero totale di errori per il recupero di foto da Active Directory  <br/> |
|Numero di errori di ricerca dei contatti  <br/> |Numero totale di errori per cercare i contatti in Exchange  <br/> |
|Numero di errori di deserializzazione  <br/> |Numero totale di errori di deserializzazione  <br/> |
|Numero di errori di ottenimento della foto HD  <br/> |Numero totale di errori per recuperare le foto HD da Exchange  <br/> |
|Oltre il numero massimo di abbonamenti per applicazione  <br/> |Numero di richieste di sottoscrizione sul massimo consentito per ogni applicazione  <br/> |
|Oltre il numero massimo di abbonamenti per batch  <br/> |Numero di richieste di sottoscrizione sul massimo consentito per batch  <br/> |
|Errori di sottoscrizione presenza  <br/> |Numero di errori di sottoscrizione della presenza  <br/> |
|Registrazione degli errori di endpoint  <br/> |Numero di errori per la registrazione degli endpoint  <br/> |
|Richieste ricevute/seconde  <br/> |Tasso per secondo delle richieste ricevute  <br/> |
|Richieste succeeded/Second  <br/> |Il tasso per secondo delle richieste di successo (codici di risposta HTTP 2xx/3xx)  <br/> |
|Succeeded Create application requests/Second  <br/> |Tasso per secondo delle richieste di creazione di applicazioni di successo  <br/> |
|Conteggio scaduto in sospeso  <br/> |Il numero di operazioni in sospeso viene scaduta  <br/> |
|Totale richieste di creazione di applicazioni ricevute  <br/> |Numero totale di richieste di creazione di applicazioni ricevute dopo l'avvio del servizio  <br/> |
|Risposte 4xx totali HTTP  <br/> |Numero totale di risposte 4xx HTTP  <br/> |
|Risposte 5xx totali HTTP  <br/> |Numero totale di risposte 5xx HTTP  <br/> |
|Totale richieste ricevute nel canale di comando  <br/> |Numero totale di richieste ricevute nel canale di comando  <br/> |
|Totale richieste riuscite  <br/> |Numero totale di richieste che sono state riuscite  <br/> |
|Totale delle sessioni avviate  <br/> |Numero totale di sessioni avviate dopo l'avvio del servizio  <br/> |
|Totale delle sessioni terminate a causa del timeout inattivo  <br/> |Numero totale di sessioni terminate a causa del timeout di inattività dell'utente  <br/> |
|Totale applicazioni a limitazione  <br/> |Numero di applicazioni limitate  <br/> |
   
**Contatori delle prestazioni per il servizio di mobilità MCX**

|**Contatore**|**Descrizione**|
|:-----|:-----|
|Durata media per una sessione in millisecondi  <br/> |Durata media per una sessione in millisecondi  <br/> |
|Abbonamenti alle notifiche push correnti  <br/> |Numero corrente di abbonamenti alle notifiche push. Questo numero, in combinazione con il conteggio delle sessioni attivo, rappresenta il sottoinsieme delle sessioni attualmente attive registrate per i dispositivi Windows Mobile o iPhone.  <br/> |
|Conteggio del sondaggio di timeout di rete attualmente attivo  <br/> |Numero di sondaggi di rete scaduti  <br/> |
|Conteggio sondaggi attualmente attivi  <br/> |Numero di sondaggi attualmente attivi (connessioni a lungo termine al server)  <br/> |
|Conteggio sessioni attualmente attivo  <br/> |Numero corrente di endpoint registrati nel servizio mobilità  <br/> |
|Conteggio sessioni attivo con abbonamenti alla presenza attiva  <br/> |Numero di sessioni attualmente attive con abbonamenti a presenza attiva  <br/> |
|Richieste di notifica push fallite/seconde  <br/> |Frequenza per il secondo delle notifiche push non riuscite  <br/> |
|Richieste di notifica push succeeded/Second  <br/> |Il tasso al secondo delle notifiche push di successo  <br/> |
|Richieste di notifica push Throttled/Second  <br/> |Il tasso al secondo delle notifiche push limitate  <br/> |
|Richieste di notifica push/secondo  <br/> |Il tasso al secondo delle notifiche push inviate  <br/> |
|Richieste non riuscite/secondo  <br/> |Tasso per secondo delle richieste non riuscite  <br/> |
|Richieste ricevute/seconde  <br/> |Tasso per secondo delle richieste ricevute  <br/> |
|Richieste rifiutate/seconde  <br/> |Tasso al secondo delle richieste rifiutate  <br/> |
|Richieste succeeded/Second  <br/> |Il tasso al secondo delle richieste di successo  <br/> |
|Le richieste di sessione avviate sono successe al secondo  <br/> |Il tasso al secondo delle richieste di posizione di ottenimento riuscito. Le richieste di avvio di una sessione utilizzano la maggior parte della CPU nel server. Il carico supportato di picco è 12/secondo. La sostenibilità dipende da altri carichi nel server. L'avvio di una sessione in genere indica un accesso per un utente che è stato disconnesso per un periodo di tempo prolungato.  <br/> |
|Chiamate vocali in ingresso rifiutate totali  <br/> |Numero totale di chiamate vocali in ingresso rifiutate  <br/> |
|Totale chiamate vocali in ingresso non riuscito  <br/> |Numero totale di chiamate vocali in ingresso non riuscite  <br/> |
|Totale chiamate vocali in uscita non riuscite  <br/> |Numero totale di chiamate vocali in uscita non riuscite  <br/> |
|Numero totale di sessioni terminate dall'utente  <br/> |Numero totale di sessioni terminate dagli utenti  <br/> |
|Totale richieste di notifica push  <br/> |Numero totale di richieste di notifica push  <br/> |
|Totale richieste di notifica push non riuscite  <br/> |Numero totale di richieste di notifica push non riuscite  <br/> |
|Totale richieste di notifica push riuscite  <br/> |Numero totale di richieste di notifica push che hanno avuto esito positivo  <br/> |
|Richieste di notifica push totali limitate  <br/> |Numero totale di richieste di notifica push che sono state strozzate  <br/> |
|Totale richieste non riuscite  <br/> |Numero totale di richieste non riuscite  <br/> |
|Totale richieste ricevute nel canale di comando  <br/> |Numero totale di richieste ricevute nel canale di comando  <br/> |
|Totale richieste rifiutate  <br/> |Numero totale di richieste rifiutate  <br/> |
|Totale richieste riuscite  <br/> |Numero totale di richieste effettuate al servizio di mobilità riuscito  <br/> |
|Numero totale avviato dalla sessione  <br/> |Numero totale di sessioni avviate da quando è stato avviato il servizio di mobilità  <br/> |
|Totale delle sessioni terminate a causa del timeout di inattività dell'utente  <br/> |Numero totale di sessioni terminate a causa del timeout di inattività dell'utente  <br/> |
|Totale successo delle chiamate vocali in entrata  <br/> |Numero totale di chiamate vocali in entrata che hanno avuto esito positivo  <br/> |
|Totale successo delle chiamate vocali in uscita  <br/> |Numero totale di chiamate vocali in uscita che hanno avuto esito positivo  <br/> |
   
> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
