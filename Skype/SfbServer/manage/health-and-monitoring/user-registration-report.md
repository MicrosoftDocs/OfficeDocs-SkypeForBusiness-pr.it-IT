---
title: Rapporto di registrazione degli utenti in Skype for Business Server
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
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Riepilogo: informazioni sul rapporto di registrazione degli utenti in Skype for Business Server.'
ms.openlocfilehash: cb732bdd10c051b35f4f2b69413168fd6515f998
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816646"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Rapporto di registrazione degli utenti in Skype for Business Server
 
**Riepilogo:** Informazioni sul rapporto di registrazione degli utenti in Skype for Business Server.
  
Il rapporto registrazione utenti fornisce una panoramica delle attività di accesso degli utenti, in particolare informazioni sul numero di utenti che hanno effettuato l'accesso a Skype for Business Server durante un periodo di tempo specificato (ogni ora, ogni giorno, ogni settimana, mensilmente). Tenere presente che il report indica solo il numero di utenti connessi. Non indica quali utenti hanno effettuato l'accesso. I rapporti di monitoraggio non forniscono informazioni sugli utenti specifici che utilizzano Skype for Business Server (e quali no). Tuttavia, è possibile ottenere una stima approssimativa delle informazioni degli utenti utilizzando il rapporto attività utente.
  
Quando si forniscono informazioni sugli accessi degli utenti, il rapporto di registrazione degli utenti disegna due distinzioni importanti. In primo luogo, interrompe gli accessi in due categorie principali: gli accessi interni e gli accessi esterni. Gli accessi interni rappresentano gli utenti che hanno effettuato l'accesso dall'interno del firewall dell'organizzazione, ovvero durante la connessione alla rete aziendale. Gli accessi esterni rappresentano gli utenti che si sono connessi dall'esterno del firewall tramite un server perimetrale (ad esempio, un utente che ha effettuato l'accesso da un Internet Café conta come un account esterno). Se è necessario sapere quanti utenti accedono dall'esterno del firewall, il rapporto registrazione utenti può fornire queste informazioni.
  
Inoltre, il rapporto registrazione utenti annota il numero di utenti attivi presenti nel corso di un determinato periodo. Un utente attivo è un utente che ha preso parte a una sessione di messaggistica istantanea, ha partecipato a una riunione di Skype for Business Server, ha effettuato o ha ricevuto una telefonata oppure ha utilizzato Skype for Business Server in altro modo durante questo periodo di tempo. Differisce da un utente che ha effettuato l'accesso, ma non si è mai avvalso effettivamente del sistema.
  
## <a name="accessing-the-user-registration-report"></a>Accesso al rapporto registrazione utenti

Il rapporto registrazione utenti è accessibile solo dalla home page Relazioni monitoraggio e non è collegato ad altri rapporti.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Utilizzo ottimale del rapporto registrazione utenti

Dopo aver distribuito Skype for Business Server, una domanda comune è la seguente: come è possibile sapere se gli utenti utilizzano effettivamente questa nuova tecnologia? Sebbene presenti qualche limitazione, il rapporto registrazione utenti può contribuire a fornire una risposta al riguardo. Per determinare se gli utenti utilizzano Skype for Business Server o meno, è necessario eseguire due operazioni. Innanzitutto, occorre acquisire il valore metrico degli utenti con accesso univoco dal rapporto registrazione utenti. Questo valore indica il numero di utenti distinti che hanno effettuato l'accesso a Skype for Business Server.
  
In base al confronto, la metrica totale degli accessi indica il numero totale di volte in cui tutti gli utenti hanno effettuato l'accesso a Skype for Business Server. Si supponga, ad esempio, che Ken si sia connesso a Skype for Business Server cinque volte diverse in un solo giorno. In tal caso, Ken remario conta come cinque sessioni di accesso separate per la metrica totale degli accessi, ma un solo utente di accesso per la metrica degli utenti di accesso univoco. Analogamente, non è raro che un utente acceda da più dispositivi o più posizioni. Ad esempio, un utente può accedere usando il proprio computer desktop, il suo computer portatile e può disporre di un telefono IP che accede automaticamente a Skype for Business Server. In questo esempio, è presente un utente univoco con tre accessi.
  
Per spiegare ulteriormente la differenza tra accessi totali e accessi univoci, osservare gli accessi relativi a uno specifico periodo nella tabella seguente.
  
|**Utente**|**Ora accesso**|
|:-----|:-----|
|Davide Garghentini  <br/> |7/7/2015 8:45 AM  <br/> |
|Davide Garghentini  <br/> |7/7/2015 8:46 AM  <br/> |
|Daniela Cazzaniga  <br/> |7/7/2015 9:17 AM  <br/> |
|Davide Garghentini  <br/> |7/7/2015 9:22 AM  <br/> |
|Daniela Cazzaniga  <br/> |7/7/2015 9:31 AM  <br/> |
   
Sebbene complessivamente vengano indicati cinque accessi, vi sono in realtà solo due utenti con accesso univoco: Davide Garghentini, che si è connesso tre volte, e Luisa Cazzaniga, che ha effettuato l'accesso due volte. Questa è la differenza tra accessi e utenti con accesso univoco.
  
Oltre a conoscere il numero di accessi univoci, è necessario conoscere il numero totale di utenti che sono stati abilitati per Skype for Business Server. Tale valore può essere recuperato aprendo Skype for Business Server Management Shell ed eseguendo il comando di Windows PowerShell seguente:
  
```PowerShell
(Get-CsUser).Count
```

Se il comando precedente restituisce un valore pari a 1.236 e la metrica degli utenti di accesso univoco restituisce un valore medio di 667, il che indica che un po' più della metà degli utenti abilitati per Skype for business si sta effettivamente accedendo al sistema ogni giorno (ovvero 667 diviso per 1.236, che corrisponde a circa 54%).
  
> [!CAUTION]
> Tenere presente che le metriche di accesso registrano gli utenti effettivamente connessi durante il periodo di tempo specificato. Non tengono conto degli utenti già connessi al sistema. Ad esempio, se la metrica degli utenti di accesso univoco Visualizza 667 accessi e sono presenti 1.236 utenti, questo suggerisce che circa la metà degli utenti accedono al sistema. Tuttavia, si supponga che 300 utenti siano già connessi al sistema al momento in cui si è iniziato a controllare i dati di accesso. Questo significa che si è effettivamente avuto quasi 1.000 utenti connessi a Skype for Business Server, il che significherebbe che più vicino al 80% degli utenti sono stati connessi. 
  
È inoltre opportuno confrontare i valori delle metriche Utenti con accesso univoco e Utenti attivi univoci. La metrica Unique Active users indica quanti utenti univoci hanno effettivamente utilizzato Skype for Business Server: hanno fatto una telefonata, hanno partecipato a una riunione di Skype for Business Server o sono stati presenti in una sessione di messaggistica istantanea. Si tratta di informazioni utili, perché è possibile configurare Skype for Business Server per l'avvio automatico ogni volta che un utente avvia Windows. Per questo motivo, potrebbe essere presente un numero elevato di utenti che accedono automaticamente a Skype for business quando accedono a Windows ogni giorno, ma non utilizzano mai effettivamente Skype for Business Server durante tale periodo di tempo.
  
La metrica degli utenti attivi univoci fornisce anche dati più significativi in un'organizzazione in cui gli utenti in genere non disattivano le finestre alla fine della giornata. Al contrario, bloccano semplicemente i propri computer e lasciano Windows e Skype for business in esecuzione. In una situazione simile, si potrebbe finire con pochissimi accessi al giorno perché gli utenti hanno effettuato l'accesso alcuni giorni fa e non sono mai disconnessi. Tuttavia, gli utenti attivi unici indicano se gli utenti utilizzano attivamente Skype for business o un altro client Skype for Business Server.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Ad esempio, il rapporto di registrazione degli utenti consente di visualizzare i dati per tutti i pool di registrazione e i server perimetrali o per visualizzare i dati per un singolo pool. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In tal caso, le registrazioni vengono raggruppate in base all'ora, al giorno, alla settimana o al mese.
  
Nella tabella seguente sono riportati i filtri che è possibile utilizzare con il rapporto registrazione utenti.
  
**Filtri per il rapporto registrazione utenti**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Intervallo** <br/> | Selezionare uno dei seguenti: <br/>  Orario (è possibile visualizzare un massimo di 25 ore) <br/>  Giornaliero (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (è possibile visualizzare un massimo di 12 settimane) <br/>  Mensile (è possibile visualizzare un massimo di 12 mesi) <br/>  Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Ad esempio, se si seleziona l'intervallo giornaliero con una data di inizio pari a 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni da 8/7/2015 12:00 a 9/7/2015 12:00 (ovvero un totale di dati di 31 giorni). <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure selezionare **[Tutto]** per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database. <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente vengono riportate le informazioni fornite nel rapporto registrazione utenti. 
  
**Metrica del rapporto registrazione utenti**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Orario** <br/> **Giornaliero** <br/> **Settimanale** <br/> **Mensile** <br/> |No  <br/> |Indica l'intervallo di tempo selezionato sulla barra degli strumenti dei filtri. Ove applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate relative a tale intervallo. Ad esempio, se si utilizza l'intervallo giornaliero e si fa clic su 7/7/2015, viene visualizzata una ripartizione oraria dell'attività di registrazione degli utenti per tale data.  <br/> |
|**Totale accessi** <br/> |No  <br/> |Numero totale di sessioni di accesso che hanno avuto esito positivo.  <br/> |
|**Accessi interni** <br/> |No  <br/> |Numero totale di accessi nella rete interna.  <br/> |
|**Accessi esterni** <br/> |No  <br/> |Numero totale di accessi dal di fuori della rete interna, utilizzando il server perimetrale.  <br/> |
|**Utenti con accesso univoco** <br/> |No  <br/> |Numero totale di utenti che hanno avuto almeno una sessione di accesso. Un utente che ha avuto più sessioni di accesso viene considerato come un unico utente, al pari di una persona che ha avuto una sola sessione di accesso.  <br/> |
|**Utenti attivi univoci** <br/> |No  <br/> |Numero totale di utenti che sono stati coinvolti in una sessione peer-to-peer o di conferenza. Un utente che ha avuto più sessioni viene considerato come un unico utente, al pari di una persona che ha avuto una sola sessione.  <br/> |
   

