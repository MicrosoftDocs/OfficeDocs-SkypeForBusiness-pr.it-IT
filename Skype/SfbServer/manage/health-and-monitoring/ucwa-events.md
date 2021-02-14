---
title: Eventi UCWA in Skype for Business Server
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
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Riepilogo: informazioni su Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: d8426418bf01954137a1bbed25d5fef93443dc5c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816666"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventi UCWA in Skype for Business Server
 
**Riepilogo:** Informazioni su Unified Communications Web API (UCWA) in Skype for Business Server.
  
Skype for Business Server utilizza Unified Communications Web API (UCWA) per diversi scopi, dall'accesso a Microsoft Exchange per le ricerche dei contatti all'aggiornamento della presenza per i client mobili.
  
UCWA scriverà record di comportamento operativo come tipi di evento Informativo, Avviso ed Errore. Nella tabella seguente vengono descritti gli eventi che possono essere scritti dai componenti UCWA.
  
|**ID evento**|**Tipo evento**|**Riepilogo**|**Causa e risoluzione**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informativo  <br/> |UCWA inizializzato  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Errore  <br/> |UCWA ha rilevato un'eccezione imprevista durante l'inizializzazione  <br/> |Si è verificato un errore imprevisto durante l'inizializzazione  <br/> Esaminare i dettagli dell'eccezione nella voce del registro eventi associata per determinare la possibile causa  <br/> |
|20003  <br/> |Errore  <br/> |UCWA ha rilevato un'eccezione non gestita  <br/> |Si è verificata un'eccezione non gestita  <br/> Riavviare il server. Se il problema persiste, contattare il supporto tecnico  <br/> |
|20004  <br/> |Errore  <br/> |Impossibile accedere a Exchange per foto HD  <br/> |Connessione a Exchange non disponibile  <br/> Verificare che la connessione a Exchange sia disponibile  <br/> |
|20005  <br/> |Informativo  <br/> |Ripristino dall'accesso a Exchange per foto HD  <br/> |N/D  <br/> |
|20006  <br/> |Errore  <br/> |Impossibile accedere a Exchange per la ricerca di contatti  <br/> |Connessione a Exchange non disponibile  <br/> Verificare che la connessione a Exchange sia disponibile  <br/> |
|20007  <br/> |Informativo  <br/> |Ripristino dall'esito negativo della ricerca del contatto in Exchange  <br/> |N/D  <br/> |
|20008  <br/> |Avviso  <br/> |Tentare di sottoscrivere più sottoscrizioni di presenza consentite per ogni applicazione  <br/> |Tentare di sottoscrivere più sottoscrizioni di presenza consentite per ogni applicazione  <br/> Verificare la presenza di sottoscrizioni non necessarie nei client  <br/> |
|20009  <br/> |Avviso  <br/> |Tentare di sottoscrivere più sottoscrizioni di presenza consentite per batch  <br/> |Tentare di sottoscrivere più sottoscrizioni di presenza consentite per batch  <br/> Verificare la presenza di sottoscrizioni non necessarie nei client  <br/> |
|20010  <br/> |Errore  <br/> |Impossibile recuperare dati in banda  <br/> |Impossibile recuperare dati in banda  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
|20011  <br/> |Errore  <br/> |Impossibile sottoscrivere la presenza  <br/> |Impossibile sottoscrivere la presenza  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
|20012  <br/> |Errore  <br/> |Impossibile registrare l'endpoint  <br/> |Impossibile registrare l'endpoint  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
|20013  <br/> |Errore  <br/> |MCU im non disponibile  <br/> |MCU im non disponibile  <br/> Verificare se la MCU di messaggistica istantanea è in esecuzione  <br/> |
|20014  <br/> |Informativo  <br/> |Ripristino dalla mancata connessione alla MCU di messaggistica istantanea  <br/> |N/D  <br/> |
|20015  <br/> |Errore  <br/> |AV MCU non disponibile  <br/> |AV MCU non disponibile  <br/> Verificare se AV MCU è in esecuzione  <br/> |
|20016  <br/> |Informativo  <br/> |Ripristino dall'errore di connessione a AV MCU  <br/> |N/D  <br/> |
|20017  <br/> |Errore  <br/> |AS MCU is unavailable  <br/> |AS MCU is unavailable  <br/> Verificare se AS MCU è in esecuzione  <br/> |
|20018  <br/> |Informativo  <br/> |Ripristino dall'errore di connessione a AS MCU  <br/> |N/D  <br/> |
|20019  <br/> |Errore  <br/> |MCU dei dati non disponibile  <br/> |MCU dei dati non disponibile  <br/> Verificare se Data MCU è in esecuzione  <br/> |
|20020  <br/> |Informativo  <br/> |Ripristino dall'errore di connessione a MCU dati  <br/> |N/D  <br/> |
|20021  <br/> |Errore  <br/> |Impossibile partecipare a MCU di messaggistica istantanea  <br/> |Impossibile partecipare a MCU di messaggistica istantanea  <br/> Verificare se la MCU di messaggistica istantanea è in esecuzione  <br/> |
|20022  <br/> |Errore  <br/> |Impossibile partecipare a AV MCU  <br/> |Impossibile partecipare a AV MCU  <br/> Verificare se AV MCU è in esecuzione  <br/> |
|20023  <br/> |Errore  <br/> |Impossibile partecipare come MCU  <br/> |Impossibile partecipare come MCU  <br/> Verificare se AS MCU è in esecuzione  <br/> |
|20024  <br/> |Errore  <br/> |Cannot join Data MCU  <br/> |Cannot join Data MCU  <br/> Verificare se Data MCU è in esecuzione  <br/> |
|20025  <br/> |Errore  <br/> |Impossibile accedere ad Active Directory per la foto  <br/> |Connessione ad Active Directory non disponibile  <br/> Verificare che la connessione ad Active Directory sia disponibile  <br/> |
|20026  <br/> |Informativo  <br/> |È stato ripristinato dall'errore di accesso ad Active Directory per la foto  <br/> |N/D  <br/> |
|20027  <br/> |Avviso  <br/> |Impossibile deserializzare  <br/> |Impossibile deserializzare  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
   

