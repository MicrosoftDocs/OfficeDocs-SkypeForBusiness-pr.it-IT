---
title: Contatori delle prestazioni per dispositivi mobili in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Riepilogo: informazioni sui contatori delle prestazioni che è possibile utilizzare per monitorare i server che eseguono UCWA (Unified Communications Web API) e il Skype for Business Server Mcx Mobility Service.'
ms.openlocfilehash: 4ea7ba3f7c4d9685fe01c64157324a64f823c5bc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578780"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Contatori delle prestazioni per dispositivi mobili in Skype for Business Server
 
**Riepilogo:** Informazioni sui contatori delle prestazioni che è possibile utilizzare per monitorare i server che eseguono UCWA (Unified Communications Web API) e il Skype for Business Server Mcx Mobility Service.
  
Nelle tabelle seguenti sono elencati i nomi e le descrizioni dei contatori delle prestazioni che è possibile utilizzare per monitorare i server che eseguono UCWA (Unified Communications Web API) e il servizio Skype for Business Server Mcx Mobility. 
  
Il nome della categoria per i contatori nella tabella UCWA è **LS:WEB - UCWA.**
  
Il nome della categoria per i contatori nella tabella Mcx Mobility Service è **LS:WEB - Mobile Communication Service.**

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="performance-counters-for-ucwa"></a>Contatori delle prestazioni per UCWA

|Contatore|Descrizione|
|:-----|:-----|
|Conteggio applicazioni attive  <br/> |Numero corrente di applicazioni  <br/> |
|Conteggio modalità condivisione applicazioni attive  <br/> |Numero corrente di modalità condivisione applicazioni  <br/> |
|Conteggio modalità audio attivo  <br/> |Numero corrente di modalità audio  <br/> |
|Conteggio modalità collaborazione dati attiva  <br/> |Numero corrente di modalità di collaborazione dati  <br/> |
|Latenza get foto di Active Directory (ms)  <br/> |Questo contatore indica il tempo medio (in millisecondi) per recuperare una foto da Active Directory  <br/> |
|Conteggio modalità di messaggistica attiva  <br/> |Numero corrente di modalità di messaggistica  <br/> |
|Conteggio modalità video panoramico attivo  <br/> |Numero corrente di modalità Panoramic Video  <br/> |
|Conteggio get in sospeso attivo  <br/> |Numero di richieste in sospeso attualmente attive. connessioni di lunga durata al server  <br/> |
|Conteggio sessioni attive  <br/> |Numero corrente di endpoint registrati in UCWA per applicazione e totale  <br/> |
|Conteggio istanze utente attive  <br/> |Numero corrente di istanze utente  <br/> |
|Istanze utente attive senza applicazione  <br/> |Numero corrente di istanze utente senza applicazione  <br/> |
|Conteggio modalità video attivo  <br/> |Numero corrente di modalità video  <br/> |
|Richieste di creazione applicazioni ricevute al secondo  <br/> |Frequenza al secondo delle richieste di creazione di applicazioni ricevute  <br/> |
|AS MCU Join Failures  <br/> |Numero di errori di aggiunta MCU AS  <br/> |
|Errori di aggiunta av MCU  <br/> |Numero di errori di aggiunta av MCU  <br/> |
|Tempo medio di avvio applicazione (ms)  <br/> |Tempo medio di avvio dell'applicazione in millisecondi  <br/> |
|Durata media per sessione (ms)  <br/> |Durata media di una sessione in millisecondi  <br/> |
|Errori di join MCU dati  <br/> |Numero di errori di join MCU dati  <br/> |
|Exchange Latenza ricerca contatti (ms)  <br/> |Questo contatore indica il tempo medio in millisecondi per la ricerca del contatto in Exchange  <br/> |
|Exchange Latenza get foto HD (ms)  <br/> |Questo contatore indica il tempo medio in millisecondi per recuperare una foto da Exchange  <br/> |
|Risposte HTTP 4xx/secondo  <br/> |Frequenza al secondo di risposte con codice HTTP 4xx  <br/> |
|Risposte HTTP 5xx/secondo  <br/> |Frequenza al secondo di risposte con codice HTTP 5xx  <br/> |
|Errori di aggiunta MCU di messaggistica istantanea  <br/> |Numero di errori di aggiunta MCU di messaggistica istantanea  <br/> |
|Numero di errori di get di foto di Active Directory  <br/> |Numero totale di errori durante il recupero delle foto da Active Directory  <br/> |
|Numero di errori di ricerca contatti  <br/> |Numero totale di errori di ricerca dei contatti in Exchange  <br/> |
|Numero di errori di deserializzazione  <br/> |Numero totale di errori di deserializzazione  <br/> |
|Numero di errori di hd photo get  <br/> |Numero totale di errori durante il recupero delle foto HD da Exchange  <br/> |
|Oltre il numero massimo di sottoscrizioni per applicazione  <br/> |Numero di richieste di sottoscrizione oltre il numero massimo consentito per ogni applicazione  <br/> |
|Oltre il numero massimo di sottoscrizioni per batch  <br/> |Numero di richieste di sottoscrizione oltre il numero massimo consentito per batch  <br/> |
|Errori sottoscrizione presenza  <br/> |Numero di errori durante la sottoscrizione della presenza  <br/> |
|Registrazione degli errori degli endpoint  <br/> |Numero di errori di registrazione degli endpoint  <br/> |
|Richieste ricevute/secondo  <br/> |Frequenza al secondo di richieste ricevute  <br/> |
|Richieste riuscite/secondo  <br/> |Frequenza al secondo di richieste riuscite (codici di risposta HTTP 2xx/3xx)  <br/> |
|Creazione richieste applicazioni completata/secondo  <br/> |Frequenza al secondo di richieste di creazione di applicazioni riuscite  <br/> |
|Timeout conteggio get in sospeso  <br/> |Il numero di richieste in sospeso che si sono timeout  <br/> |
|Totale richieste di creazione applicazioni ricevute  <br/> |Numero totale di richieste di creazione di applicazioni ricevute dall'avvio del servizio  <br/> |
|Totale risposte HTTP 4xx  <br/> |Numero totale di risposte HTTP 4xx  <br/> |
|Totale risposte HTTP 5xx  <br/> |Numero totale di risposte HTTP 5xx  <br/> |
|Totale richieste ricevute nel canale di comando  <br/> |Numero totale di richieste ricevute nel canale di comando  <br/> |
|Totale richieste riuscite  <br/> |Numero totale di richieste riuscite  <br/> |
|Totale sessioni avviate  <br/> |Numero totale di sessioni avviate dall'avvio del servizio  <br/> |
|Totale sessioni terminate a causa del timeout di inattività  <br/> |Numero totale di sessioni terminate a causa del timeout di inattività dell'utente  <br/> |
|Totale applicazioni limitate  <br/> |Numero di applicazioni limitate  <br/> |
   
**Contatori delle prestazioni per il servizio Mcx Mobility**

|**Contatore**|**Descrizione**|
|:-----|:-----|
|Durata media di una sessione in millisecondi  <br/> |Durata media di una sessione in millisecondi  <br/> |
|Sottoscrizioni alle notifiche Push correnti  <br/> |Numero corrente di sottoscrizioni di notifica push. Questo numero, in combinazione con Conteggio sessioni attualmente attive, rappresenta il sottoinsieme di sessioni attualmente attive registrate per Windows dispositivi mobili o iPhone mobili.  <br/> |
|Conteggio polling timeout rete attualmente attivo  <br/> |Il numero di polling di rete che si sono timeout  <br/> |
|Conteggio polling attualmente attivo  <br/> |Numero di polling attualmente attivi (connessioni di lunga durata al server)  <br/> |
|Conteggio sessioni attualmente attive  <br/> |Numero corrente di endpoint registrati nel servizio per dispositivi mobili  <br/> |
|Conteggio sessioni attualmente attive con sottoscrizioni presenza attive  <br/> |Numero di sessioni attualmente attive con sottoscrizioni di presenza attive  <br/> |
|Richieste di notifica Push non riuscite al secondo  <br/> |Frequenza al secondo di notifiche push non riuscite  <br/> |
|Richieste di notifica Push riuscite al secondo  <br/> |Frequenza al secondo di notifiche push riuscite  <br/> |
|Richieste di notifica Push limitate al secondo  <br/> |Frequenza al secondo di notifiche push limitate  <br/> |
|Richieste di notifica Push al secondo  <br/> |Frequenza al secondo di notifiche push inviate  <br/> |
|Richieste non riuscite/secondo  <br/> |Frequenza al secondo di richieste non riuscite  <br/> |
|Richieste ricevute/secondo  <br/> |Frequenza al secondo di richieste ricevute  <br/> |
|Richieste rifiutate al secondo  <br/> |Frequenza al secondo di richieste rifiutate  <br/> |
|Richieste riuscite/secondo  <br/> |Frequenza al secondo di richieste riuscite  <br/> |
|Richieste di sessione al secondo avviate con esito positivo  <br/> |Frequenza al secondo di richieste Get Location riuscite. Le richieste di avvio di una sessione utilizzano la maggior parte della CPU nel server. Il carico supportato di picco è 12/secondo. La sustainability dipende da altri carichi sul server. Avviare una sessione in genere significa un accesso per un utente che è stato disconnesso per un lungo periodo di tempo.  <br/> |
|Totale chiamate vocali in ingresso rifiutate  <br/> |Numero totale di chiamate vocali in ingresso rifiutate  <br/> |
|Totale chiamate vocali in ingresso non riuscite  <br/> |Numero totale di chiamate vocali in ingresso non riuscite  <br/> |
|Totale chiamate vocali in uscita non riuscite  <br/> |Numero totale di chiamate vocali in uscita non riuscite  <br/> |
|Numero totale di sessioni terminate dall'utente  <br/> |Numero totale di sessioni terminate dagli utenti  <br/> |
|Totale richieste di notifica Push  <br/> |Numero totale di richieste di notifica push  <br/> |
|Totale richieste di notifica Push non riuscite  <br/> |Numero totale di richieste di notifica push non riuscite  <br/> |
|Totale richieste di notifica Push riuscite  <br/> |Numero totale di richieste di notifica push riuscite  <br/> |
|Totale richieste di notifica Push limitate  <br/> |Numero totale di richieste di notifica push limitate  <br/> |
|Totale richieste non riuscite  <br/> |Numero totale di richieste non riuscite  <br/> |
|Totale richieste ricevute nel canale di comando  <br/> |Numero totale di richieste ricevute nel canale di comando  <br/> |
|Totale richieste rifiutate  <br/> |Numero totale di richieste rifiutate  <br/> |
|Totale richieste riuscite  <br/> |Numero totale di richieste effettuate al servizio per dispositivi mobili riuscite  <br/> |
|Conteggio totale sessioni avviate  <br/> |Numero totale di sessioni avviate dall'avvio del servizio per dispositivi mobili  <br/> |
|Totale sessioni terminate a causa del timeout di inattività dell'utente  <br/> |Numero totale di sessioni terminate a causa del timeout di inattività dell'utente  <br/> |
|Totale chiamate vocali in ingresso riuscite  <br/> |Numero totale di chiamate vocali in ingresso riuscite  <br/> |
|Totale chiamate vocali in uscita riuscite  <br/> |Numero totale di chiamate vocali in uscita riuscite  <br/> |
   
> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
