---
title: Rapporto di registrazione utente in Skype for Business Server
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
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Riepilogo: informazioni sul Rapporto registrazione utenti in Skype for Business Server.'
ms.openlocfilehash: 6424d3b0c90bf8b9286f03f7997e286b38193d6d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593680"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Rapporto di registrazione utente in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto registrazione utenti in Skype for Business Server.
  
Il Rapporto registrazione utenti fornisce una panoramica dell'attività di accesso degli utenti, in particolare informazioni sul numero di utenti che hanno eseguito l'accesso a Skype for Business Server durante un periodo di tempo specificato (ogni ora, ogni giorno, settimanalmente, mensilmente). Tenere presente che il report indica solo il numero di persone che hanno eseguito l'accesso. Non viene specificato quali utenti hanno effettuato l'accesso. I report di monitoraggio non forniscono informazioni su quali utenti specifici usano Skype for Business Server (e quali non lo sono). Tuttavia, è possibile ottenere una stima approssimativa delle informazioni utente utilizzando il Rapporto attività utente.
  
Quando si forniscono informazioni sugli accessi degli utenti, il Rapporto registrazione utenti fa due importanti distinzioni. Innanzitutto, suddivide gli accessi in due categorie principali: accessi interni e accessi esterni. Gli accessi interni rappresentano gli utenti che hanno eseguito l'accesso dall'interno del firewall dell'organizzazione, ovvero mentre sono connessi alla rete aziendale. Gli accessi esterni rappresentano gli utenti che hanno eseguito l'accesso dall'esterno del firewall tramite un server perimetrale(ad esempio, un utente che ha eseguito l'accesso da un Internet café viene conteggiato come accesso esterno). Se è necessario conoscere il numero di utenti connessi dall'esterno del firewall, il Rapporto registrazione utenti può fornire queste informazioni.
  
Inoltre, il rapporto registrazione utenti annota il numero di utenti attivi presenti nel corso di un determinato periodo. Un utente attivo è un utente che ha partecipato a una sessione di messaggistica istantanea, ha partecipato a una riunione di Skype for Business Server, ha effettuato o ricevuto una chiamata telefonica o ha utilizzato in altro modo Skype for Business Server durante tale periodo di tempo. Differisce da un utente che ha effettuato l'accesso, ma non si è mai avvalso effettivamente del sistema.
  
## <a name="accessing-the-user-registration-report"></a>Accesso al rapporto registrazione utenti

Il rapporto registrazione utenti è accessibile solo dalla home page Relazioni monitoraggio e non è collegato ad altri rapporti.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Utilizzo ottimale del rapporto registrazione utenti

Dopo aver distribuito Skype for Business Server una domanda comune è la seguente: Come è possibile sapere se gli utenti usano effettivamente questa nuova tecnologia? Sebbene presenti qualche limitazione, il rapporto registrazione utenti può contribuire a fornire una risposta al riguardo. Per determinare se gli utenti usano o Skype for Business Server, è necessario eseguire due operazioni. Innanzitutto, occorre acquisire il valore metrico degli utenti con accesso univoco dal rapporto registrazione utenti. Questo valore indica il numero di utenti distinti connessi a Skype for Business Server.
  
Per confronto, la metrica Totale accessi mostra il numero totale di volte in cui chiunque ha effettuato l'accesso a Skype for Business Server. Si supponga ad esempio che Ken Myer abbia effettuato l'accesso Skype for Business Server cinque volte diverse in un singolo giorno. In tal caso, Ken Myer conta come cinque sessioni di accesso separate per la metrica Totale accessi, ma solo un utente di accesso per la metrica Utenti accesso univoco. Allo stesso modo, non è raro che un utente abiliti l'accesso da più dispositivi o da più posizioni. Ad esempio, un utente può accedere utilizzando il computer desktop, il computer portatile e un telefono IP che accede automaticamente a Skype for Business Server. In questo esempio è presente un utente univoco con tre accessi.
  
Per spiegare ulteriormente la differenza tra accessi totali e accessi univoci, osservare gli accessi relativi a uno specifico periodo nella tabella seguente.
  
|**Utente**|**Ora accesso**|
|:-----|:-----|
|Davide Garghentini  <br/> |07/07/2015 08:45  <br/> |
|Davide Garghentini  <br/> |07/07/2015 08:46  <br/> |
|Daniela Cazzaniga  <br/> |07/07/2015 09:17  <br/> |
|Davide Garghentini  <br/> |07/07/2015 09:22  <br/> |
|Daniela Cazzaniga  <br/> |07/07/2015 09:31  <br/> |
   
Sebbene complessivamente vengano indicati cinque accessi, vi sono in realtà solo due utenti con accesso univoco: Davide Garghentini, che si è connesso tre volte, e Luisa Cazzaniga, che ha effettuato l'accesso due volte. Questa è la differenza tra accessi e utenti con accesso univoco.
  
Oltre a conoscere il numero di accessi univoci, è necessario conoscere il numero totale di utenti abilitati per Skype for Business Server. Tale valore può essere recuperato aprendo Skype for Business Server Management Shell ed eseguendo il comando Windows PowerShell seguente:
  
```PowerShell
(Get-CsUser).Count
```

Se il comando precedente restituisce un valore pari a 1.236 e la metrica Utenti accesso univoco restituisce un valore medio di 667, ciò suggerisce che poco più della metà degli utenti abilitati per Skype for Business sta effettivamente accedendo al sistema ogni giorno (ovvero 667 diviso per 1.236, ovvero circa il 54%).
  
> [!CAUTION]
> Tenere presente che le metriche di accesso registrano gli utenti che hanno effettivamente eseguito l'accesso durante il periodo di tempo specificato. Non tengono traccia degli utenti già connessi al sistema. Ad esempio, se la metrica Utenti accesso univoco mostra 667 accessi e sono presenti 1.236 utenti, ciò suggerisce che circa la metà degli utenti accede al sistema. Si supponga tuttavia che 300 utenti fossero già connessi al sistema al momento in cui è stato avviato il controllo dei dati di accesso. Ciò significa che in realtà quasi 1.000 utenti hanno effettuato l'accesso a Skype for Business Server, il che significa che quasi l'80% degli utenti ha effettuato l'accesso. 
  
È inoltre opportuno confrontare i valori delle metriche Utenti con accesso univoco e Utenti attivi univoci. La metrica Utenti attivi univoci indica quanti utenti univoci hanno effettivamente usato Skype for Business Server: hanno effettuato una chiamata telefonica, hanno partecipato a una riunione di Skype for Business Server o hanno partecipato a una sessione di messaggistica istantanea. Si tratta di informazioni utili, Skype for Business Server possono essere configurate per l'avvio automatico ogni volta che un utente Windows. Per questo, è possibile che un numero elevato di utenti a cui si accede automaticamente a Skype for Business quando accede a Windows ogni giorno, ma non utilizzi mai Skype for Business Server durante tale periodo di tempo.
  
La metrica Utenti attivi univoci fornisce anche dati più significativi in un'organizzazione in cui gli utenti in genere non si discostono Windows alla fine della giornata. Al contrario, bloccano semplicemente i computer e lasciano Windows e Skype for Business in esecuzione. In una situazione del genere, si potrebbe finire con pochi accessi al giorno perché gli utenti si sono connessi diversi giorni fa e non si sono mai disconnessi. Tuttavia, Utenti attivi univoci indica se gli utenti usano attivamente Skype for Business o un altro client Skype for Business Server.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Ad esempio, il Rapporto registrazione utenti consente di visualizzare i dati per tutti i pool di registrazione e i server perimetrali oppure di visualizzare i dati per un singolo pool. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In tal caso, le registrazioni vengono raggruppate in base all'ora, al giorno, alla settimana o al mese.
  
Nella tabella seguente sono riportati i filtri che è possibile utilizzare con il rapporto registrazione utenti.
  
**Filtri per il rapporto registrazione utenti**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Interval** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 7/07/2015 e data di fine 28/02/2015, verranno visualizzati i dati relativi ai giorni 07/08/2015 12.00 alle 07.00.00 12.00 (ovvero un totale di 31 giorni di dati). <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure selezionare **[Tutto]** per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database. <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente vengono riportate le informazioni fornite nel rapporto registrazione utenti. 
  
**Metrica del rapporto registrazione utenti**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Orario** <br/> **Giornaliero** <br/> **Settimanale** <br/> **Mensile** <br/> |No  <br/> |Indica l'intervallo di tempo selezionato sulla barra degli strumenti dei filtri. Ove applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate relative a tale intervallo. Ad esempio, se si utilizza l'intervallo Giornaliero e si fa clic su 7/07/07/2015, verrà visualizzata una suddivisione oraria dell'attività di registrazione degli utenti per tale data.  <br/> |
|**Totale accessi** <br/> |No  <br/> |Numero totale di sessioni di accesso che hanno avuto esito positivo.  <br/> |
|**Accessi interni** <br/> |No  <br/> |Numero totale di accessi nella rete interna.  <br/> |
|**Accessi esterni** <br/> |No  <br/> |Numero totale di accessi dal di fuori della rete interna, utilizzando il server perimetrale.  <br/> |
|**Utenti con accesso univoco** <br/> |No  <br/> |Numero totale di utenti che hanno avuto almeno una sessione di accesso. Un utente che ha avuto più sessioni di accesso viene considerato come un unico utente, al pari di una persona che ha avuto una sola sessione di accesso.  <br/> |
|**Utenti attivi univoci** <br/> |No  <br/> |Numero totale di utenti che sono stati coinvolti in una sessione peer-to-peer o di conferenza. Un utente che ha avuto più sessioni viene considerato come un unico utente, al pari di una persona che ha avuto una sola sessione.  <br/> |
   

