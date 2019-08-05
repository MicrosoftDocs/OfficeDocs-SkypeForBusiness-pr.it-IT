---
title: Eventi UCWA in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Riepilogo: informazioni su Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: bbded70318190fb4fa68ab524a696183c97ff07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188645"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventi UCWA in Skype for Business Server
 
**Riepilogo:** Informazioni su Unified Communications Web API (UCWA) in Skype for Business Server.
  
Skype for Business Server usa Unified Communications Web API (UCWA) per diversi scopi, dall'accesso a Microsoft Exchange per la ricerca di contatti all'aggiornamento della presenza per i client mobili.
  
UCWA scriverà i record del comportamento operativo come tipi di evento informativo, di avviso e di errore. La tabella seguente descrive gli eventi che possono essere scritti dai componenti UCWA.
  
|**ID evento**|**Tipo di evento**|**Riepilogo**|**Causa e risoluzione**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informativo  <br/> |UCWA inizializzato  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Errore  <br/> |UCWA ha rilevato un'eccezione imprevista durante l'inizializzazione  <br/> |Si è verificato un errore imprevisto durante l'inizializzazione  <br/> Esaminare i dettagli dell'eccezione nella voce del log eventi associata per determinare la causa possibile  <br/> |
|20003  <br/> |Errore  <br/> |UCWA ha rilevato un'eccezione non gestita  <br/> |È stata generata un'eccezione non gestita  <br/> Riavviare il server. Se il problema persiste, contattare il supporto tecnico  <br/> |
|20004  <br/> |Errore  <br/> |Non è possibile accedere a Exchange per la foto HD  <br/> |La connessione a Exchange non è disponibile  <br/> Verificare che la connessione a Exchange sia disponibile  <br/> |
|20005  <br/> |Informativo  <br/> |Recupero della mancata accesso a Exchange per la foto HD  <br/> |N/D  <br/> |
|20006  <br/> |Errore  <br/> |Non è possibile accedere a Exchange per la ricerca di contatti  <br/> |La connessione a Exchange non è disponibile  <br/> Verificare che la connessione a Exchange sia disponibile  <br/> |
|20007  <br/> |Informativo  <br/> |Recuperato dalla mancata ricerca del contatto in Exchange  <br/> |N/D  <br/> |
|20008  <br/> |Avviso  <br/> |Tentativo di sottoscrizione di un numero maggiore di abbonamenti a presenza consentiti per applicazione  <br/> |Tentativo di sottoscrizione di un numero maggiore di abbonamenti a presenza consentiti per applicazione  <br/> Controllare i client per gli abbonamenti non necessari  <br/> |
|20009  <br/> |Avviso  <br/> |Tentativo di sottoscrizione di un numero maggiore di abbonamenti di presenza consentiti per batch  <br/> |Tentativo di sottoscrizione di un numero maggiore di abbonamenti di presenza consentiti per batch  <br/> Controllare i client per gli abbonamenti non necessari  <br/> |
|20010  <br/> |Errore  <br/> |Non è possibile recuperare i dati in banda  <br/> |Non è possibile recuperare i dati in banda  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
|20011  <br/> |Errore  <br/> |Non è possibile sottoscrivere la presenza  <br/> |Non è possibile sottoscrivere la presenza  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
|20012  <br/> |Errore  <br/> |Impossibile registrare l'endpoint  <br/> |Impossibile registrare l'endpoint  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
|20013  <br/> |Errore  <br/> |La MCU di messaggistica istantanea non è disponibile  <br/> |La MCU di messaggistica istantanea non è disponibile  <br/> Verificare se è in corso una MCU di messaggistica istantanea  <br/> |
|20014  <br/> |Informativo  <br/> |Ripristino della mancata connessione alla MCU istantanea  <br/> |N/D  <br/> |
|20015  <br/> |Errore  <br/> |MCU AV non disponibile  <br/> |MCU AV non disponibile  <br/> Verificare se è in corso una MCU AV  <br/> |
|20016  <br/> |Informativo  <br/> |Recuperato dalla mancata connessione alla MCU AV  <br/> |N/D  <br/> |
|20017  <br/> |Errore  <br/> |Poiché MCU non è disponibile  <br/> |Poiché MCU non è disponibile  <br/> Verificare l'eventuale funzionamento di MCU  <br/> |
|20018  <br/> |Informativo  <br/> |Recuperata dalla mancata connessione a come MCU  <br/> |N/D  <br/> |
|20019  <br/> |Errore  <br/> |MCU dati non disponibile  <br/> |MCU dati non disponibile  <br/> Verificare se è in corso l'uso di MCU dati  <br/> |
|20020  <br/> |Informativo  <br/> |Recupero dalla mancata connessione a MCU dati  <br/> |N/D  <br/> |
|20021  <br/> |Errore  <br/> |Non è possibile partecipare a una MCU istantanea  <br/> |Non è possibile partecipare a una MCU istantanea  <br/> Verificare se è in corso una MCU di messaggistica istantanea  <br/> |
|20022  <br/> |Errore  <br/> |Non è possibile partecipare a MCU AV  <br/> |Non è possibile partecipare a MCU AV  <br/> Verificare se è in corso una MCU AV  <br/> |
|20023  <br/> |Errore  <br/> |Non è possibile partecipare come MCU  <br/> |Non è possibile partecipare come MCU  <br/> Verificare l'eventuale funzionamento di MCU  <br/> |
|20024  <br/> |Errore  <br/> |Non è possibile partecipare a MCU dati  <br/> |Non è possibile partecipare a MCU dati  <br/> Verificare se è in corso l'uso di MCU dati  <br/> |
|20025  <br/> |Errore  <br/> |Non è possibile accedere a Active Directory per la foto  <br/> |La connessione a Active Directory non è disponibile  <br/> Verificare che la connessione a Active Directory sia disponibile  <br/> |
|20026  <br/> |Informativo  <br/> |Recuperati dal mancato accesso a Active Directory per la foto  <br/> |N/D  <br/> |
|20027  <br/> |Avviso  <br/> |Non è possibile deserializzare  <br/> |Non è possibile deserializzare  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
   

