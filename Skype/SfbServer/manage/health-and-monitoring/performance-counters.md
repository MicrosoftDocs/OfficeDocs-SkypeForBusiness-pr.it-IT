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
localization_priority: Normal
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Riepilogo: informazioni sui contatori delle prestazioni che è possibile utilizzare per monitorare i server che eseguono Unified Communications Web API (UCWA) e il servizio per dispositivi mobili di Skype for Business Server MCX.'
ms.openlocfilehash: d711ada11cee9cb12a5cde25cab583f8b174ac50
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814406"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Contatori delle prestazioni per dispositivi mobili in Skype for Business Server
 
**Riepilogo:** Informazioni sui contatori delle prestazioni che è possibile utilizzare per monitorare i server che eseguono Unified Communications Web API (UCWA) e il servizio per dispositivi mobili di Skype for Business Server MCX.
  
Nelle tabelle riportate di seguito sono elencati i nomi e le descrizioni dei contatori delle prestazioni che è possibile utilizzare per monitorare i server che eseguono Unified Communications Web API (UCWA) e il servizio per dispositivi mobili di Skype for Business Server MCX. 
  
Il nome della categoria per i contatori nella tabella UCWA è **ls: Web-UCWA**.
  
Il nome della categoria per i contatori nella tabella dei servizi per dispositivi mobili di MCX è **ls: servizio di comunicazione web-mobile**.

> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="performance-counters-for-ucwa"></a>Contatori delle prestazioni per UCWA

|Contatore|Descrizione|
|:-----|:-----|
|Numero di applicazioni attive  <br/> |Il numero corrente di applicazioni  <br/> |
|Conteggio delle modalità di condivisione delle applicazioni attive  <br/> |Numero corrente di modalità di condivisione delle applicazioni  <br/> |
|Conteggio modalità audio attivo  <br/> |Numero corrente di modalità audio  <br/> |
|Conteggio delle modalità di collaborazione dei dati attivi  <br/> |Il numero corrente di modalità di collaborazione dei dati  <br/> |
|Latenza della foto di Active Directory (MS)  <br/> |Questo contatore indica il tempo medio (in millisecondi) per recuperare una foto da Active Directory  <br/> |
|Conteggio modalità di messaggistica attiva  <br/> |Numero corrente di modalità di messaggistica  <br/> |
|Conteggio delle modalità video panoramico attivo  <br/> |Il numero corrente di modalità video panoramico  <br/> |
|Conteggio di ottenere attivo in sospeso  <br/> |Il numero di in sospeso corrente viene attivato. connessioni Long-Held al server  <br/> |
|Conteggio delle sessioni attive  <br/> |Numero corrente di endpoint registrati in UCWA per applicazione e totale  <br/> |
|Conteggio delle istanze dell'utente attivo  <br/> |Numero corrente di istanze utente  <br/> |
|Istanze utente attive senza applicazione  <br/> |Numero corrente di istanze utente senza applicazione  <br/> |
|Conteggio delle modalità video attivo  <br/> |Il numero corrente di modalità video  <br/> |
|Richieste di creazione di applicazioni ricevute al secondo  <br/> |La percentuale di richieste di creazione di applicazioni ricevute al secondo  <br/> |
|Gli errori di join di MCU  <br/> |Numero di errori di join di MCU  <br/> |
|Errore di join di MCU AV  <br/> |Numero di errori di join di MCU AV  <br/> |
|Tempo medio di avvio dell'applicazione (MS)  <br/> |Tempo di avvio medio dell'applicazione in millisecondi  <br/> |
|Durata media della sessione (MS)  <br/> |Durata media di una sessione in millisecondi  <br/> |
|Errori di join dei dati MCU  <br/> |Numero di errori di join di MCU di dati  <br/> |
|Latenza ricerca contatti di Exchange (MS)  <br/> |Questo contatore indica il tempo medio (in millisecondi) per il contatto di ricerca in Exchange  <br/> |
|Exchange HD Photo Get latenza (MS)  <br/> |Questo contatore indica il tempo medio (in millisecondi) per il recupero di una foto da Exchange  <br/> |
|Risposte 4xx HTTP/secondo  <br/> |La percentuale di risposte al secondo con il codice 4xx HTTP  <br/> |
|Risposte 5xx HTTP/secondo  <br/> |La percentuale di risposte al secondo con il codice 5xx HTTP  <br/> |
|Errori di join di MCU IM  <br/> |Il numero di errori di join di MCU di messaggistica istantanea  <br/> |
|Numero di errori della foto di Active Directory  <br/> |Il numero totale di errori per il recupero delle foto da Active Directory  <br/> |
|Numero di errori di ricerca dei contatti  <br/> |Il numero totale di errori per la ricerca dei contatti in Exchange  <br/> |
|Numero di errori di deserializzazione  <br/> |Il numero totale di errori di deserializzazione  <br/> |
|Numero di errori di ricezione foto HD  <br/> |Il numero totale di errori per il recupero delle foto HD da Exchange  <br/> |
|Oltre il numero massimo di abbonamenti per applicazione  <br/> |Il numero di richieste di sottoscrizione sul massimo consentito per applicazione  <br/> |
|Oltre il numero massimo di sottoscrizioni per batch  <br/> |Il numero di richieste di sottoscrizione sul massimo consentito per ogni batch  <br/> |
|Errori di sottoscrizione alla presenza  <br/> |Il numero di errori da sottoscrivere la presenza  <br/> |
|Registrazione degli errori degli endpoint  <br/> |Il numero di errori di registrazione degli endpoint  <br/> |
|Richieste ricevute/secondo  <br/> |La percentuale di richieste ricevute al secondo  <br/> |
|Richieste con esito positivo/secondo  <br/> |Il tasso al secondo delle richieste riuscite (HTTP 2xx/3xx Response codes)  <br/> |
|Esito positivo della creazione delle richieste di applicazione/secondo  <br/> |La velocità al secondo delle richieste di creazione di applicazioni riuscite  <br/> |
|Conteggio scaduto in sospeso  <br/> |Il numero di in sospeso viene superato  <br/> |
|Totale richieste di creazione di applicazioni ricevute  <br/> |Il numero totale di richieste di creazione di applicazioni ricevute dopo l'avvio del servizio  <br/> |
|Totale risposte 4xx HTTP  <br/> |Il numero totale di risposte 4xx HTTP  <br/> |
|Totale risposte 5xx HTTP  <br/> |Il numero totale di risposte 5xx HTTP  <br/> |
|Totale richieste ricevute nel canale di comando  <br/> |Il numero totale di richieste ricevute nel canale di comando  <br/> |
|Totale richieste riuscite  <br/> |Il numero totale di richieste che hanno avuto esito positivo  <br/> |
|Totale sessioni avviate  <br/> |Il numero totale di sessioni avviate dopo l'avvio del servizio  <br/> |
|Totale sessioni interrotte a causa del timeout di inattività  <br/> |Il numero totale di sessioni terminate a causa del timeout di inattività dell'utente  <br/> |
|Totale applicazioni limitate  <br/> |Il numero di applicazioni limitate  <br/> |
   
**Contatori delle prestazioni per il servizio per dispositivi mobili MCX**

|**Contatore**|**Descrizione**|
|:-----|:-----|
|Durata media di una sessione in millisecondi  <br/> |Durata media di una sessione in millisecondi  <br/> |
|Abbonamenti alle notifiche push correnti  <br/> |Numero corrente di sottoscrizioni di notifica push. Questo numero, insieme al conteggio sessioni attivo, rappresenta il sottoinsieme delle sessioni attualmente attive registrate per i dispositivi Windows Mobile o iPhone.  <br/> |
|Conteggio del sondaggio del timeout di rete corrente attivo  <br/> |Il numero di polli di rete scaduti  <br/> |
|Conteggio di poll corrente attivo  <br/> |Il numero di poll attualmente attivi (connessioni di lunga durata al server)  <br/> |
|Numero di sessione corrente attivo  <br/> |Numero corrente di endpoint registrati nel servizio per dispositivi mobili  <br/> |
|Conteggio delle sessioni attivo con gli abbonamenti a presenza attiva  <br/> |Il numero di sessioni attive con sottoscrizioni di presenza attiva  <br/> |
|Richieste di notifica push non riuscite al secondo  <br/> |La percentuale di notifiche di push non riuscite al secondo  <br/> |
|Richieste di notifica push con esito positivo/secondo  <br/> |La velocità al secondo delle notifiche push con esito positivo  <br/> |
|Richieste di notifica push limitate al secondo  <br/> |La velocità al secondo delle notifiche push limitate  <br/> |
|Richieste di notifica push/secondo  <br/> |La velocità al secondo delle notifiche push inviate  <br/> |
|Richieste non riuscite al secondo  <br/> |La percentuale di richieste non riuscite al secondo  <br/> |
|Richieste ricevute/secondo  <br/> |La percentuale di richieste ricevute al secondo  <br/> |
|Richieste rifiutate/secondo  <br/> |La percentuale di richieste rifiutate al secondo  <br/> |
|Richieste con esito positivo/secondo  <br/> |Il tasso al secondo delle richieste riuscite  <br/> |
|Esito positivo delle sessioni di avvio/secondo  <br/> |La velocità al secondo delle richieste di posizione di ottenere riuscite. Le richieste di avvio di una sessione utilizzano la maggior parte della CPU sul server. Il carico supportato di picco è 12/sec. La sostenibilità dipende da altri carichi sul server. L'avvio di una sessione in genere indica un accesso per un utente che è stato disconnesso per un periodo di tempo prolungato.  <br/> |
|Totale chiamate vocali in ingresso rifiutate  <br/> |Il numero totale di chiamate vocali in ingresso rifiutate  <br/> |
|Totale chiamate vocali in ingresso non riuscite  <br/> |Numero totale di chiamate vocali in ingresso non riuscite  <br/> |
|Totale chiamate vocali in uscita non riuscite  <br/> |Il numero totale di chiamate vocali in uscita non riuscite  <br/> |
|Numero totale di sessioni terminate dall'utente  <br/> |Il numero totale di sessioni terminate dagli utenti  <br/> |
|Totale richieste di notifica push  <br/> |Il numero totale di richieste di notifica push  <br/> |
|Totale richieste di notifica push non riuscite  <br/> |Il numero totale di richieste di notifica push non riuscite  <br/> |
|Totale richieste di notifica push con esito positivo  <br/> |Il numero totale di richieste di notifica push che hanno avuto esito positivo  <br/> |
|Totale richieste di notifica push limitate  <br/> |Il numero totale di richieste di notifica push che sono state limitate  <br/> |
|Totale richieste non riuscite  <br/> |Il numero totale di richieste non riuscite  <br/> |
|Totale richieste ricevute nel canale di comando  <br/> |Il numero totale di richieste ricevute nel canale di comando  <br/> |
|Totale richieste respinte  <br/> |Il numero totale di richieste che sono state respinte  <br/> |
|Totale richieste riuscite  <br/> |Il numero totale di richieste apportate al servizio per dispositivi mobili che hanno avuto esito positivo  <br/> |
|Numero totale di sessioni avviate  <br/> |Il numero totale di sessioni avviate dopo l'avvio del servizio per dispositivi mobili  <br/> |
|Totale sessioni interrotte a causa del timeout di inattività dell'utente  <br/> |Il numero totale di sessioni terminate a causa del timeout di inattività dell'utente  <br/> |
|Totale successo delle chiamate vocali in ingresso  <br/> |Il numero totale di chiamate vocali in ingresso che hanno avuto esito positivo  <br/> |
|Numero totale di chiamate vocali in uscita  <br/> |Il numero totale di chiamate vocali in uscita che hanno avuto esito positivo  <br/> |
   
> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
