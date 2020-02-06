---
title: Pianificare il parcheggio delle chiamate in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Pianificazione di Call Park in Skype for Business Server VoIP aziendale, che consente di effettuare chiamate in attesa e di trasferire le chiamate ai reparti. Include la pianificazione della capacità, le chiamate supportate e i client supportati.
ms.openlocfilehash: 3effeab4afef60fb7a5021206d9fc3cd0227ceb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803196"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Pianificare il parcheggio delle chiamate in Skype for business
 
Pianificazione di Call Park in Skype for Business Server VoIP aziendale, che consente di effettuare chiamate in attesa e di trasferire le chiamate ai reparti. Include la pianificazione della capacità, le chiamate supportate e i client supportati.
  
L'applicazione Call Park consente agli utenti di VoIP aziendale di eseguire le operazioni seguenti:
  
- Inserire una chiamata in attesa e quindi recuperare la chiamata dallo stesso telefono o da un altro telefono.
    
- Inserire una chiamata in attesa per trasferirla in un reparto o in un'area generale, ad esempio in un reparto vendite o in un magazzino in cui è presente un telefono con area comune.
    
- Mettere una chiamata in attesa e mantenere il telefono di risposta originale gratuito per altre chiamate.
    
Quando un utente parcheggia una chiamata, Skype for Business Server trasferisce la chiamata a un numero temporaneo, detto orbita, in cui la chiamata viene mantenuta fino a quando non viene recuperata o il timeout. Skype for Business Server invia l'orbita all'utente che ha parcheggiato la chiamata. Per recuperare la chiamata parcheggiata, l'utente può selezionare il numero dell'orbita oppure fare clic sul collegamento orbita o sul pulsante nella finestra di conversazione. 
  
L'utente che ha parcheggiato una chiamata può segnalare a qualcuno di recuperare la chiamata usando un meccanismo esterno, ad esempio messaggistica istantanea (IM) o un sistema di paging, per comunicare il numero dell'orbita a qualcun altro. L'utente che ha parcheggiato la chiamata può uscire dalla finestra di conversazione per ricevere una notifica quando viene recuperata la chiamata.
  
Poiché gli intervalli di Orbit sono univoci a livello globale, è possibile recuperare le chiamate da qualsiasi sito di Skype for Business Server o telefono PBX se il routing è configurato in modo appropriato. Se non si recupera la chiamata entro un periodo di tempo configurabile, la chiamata torna alla persona che l'ha parcheggiata. Se la persona non risponde alla risponderia, la chiamata viene trasferita a una destinazione di fallback, ad esempio a un operatore, se configurata. È possibile configurare il numero di volte in cui la chiamata squilla prima di essere trasferita da uno a dieci volte. Se non si risponde a una chiamata trasferita, la chiamata viene disconnessa. L'orbita viene liberata quando la chiamata viene recuperata o disconnessa.
  
Quando si distribuisce Call Park, è necessario riservare intervalli di numeri di interno per le chiamate di parcheggio. Queste estensioni devono essere estensioni virtuali: estensioni che non hanno un utente o un telefono assegnato. Si configura quindi la tabella Orbit di Call Park con gli intervalli di numeri di interno e si specifica quale servizio applicazione ospita l'applicazione di parcheggio di chiamata che gestisce ogni intervallo. Ogni pool Front end include una tabella di parcheggio di chiamata nel server back-end corrispondente usato per gestire le chiamate parcheggiate nel pool. L'elenco di intervalli orbit è archiviato in Central Management store e viene usato per instradare le orbite al pool di destinazione. Ogni pool di Skype for Business Server in cui è distribuita e configurata l'applicazione Parcheggio di chiamata può avere uno o più intervalli di orbita. Gli intervalli di Orbit devono essere univoci a livello globale in tutta la distribuzione di Skype for Business Server. 
  
Si configurano anche altre impostazioni di Call Park, ad esempio dove vengono reindirizzate le chiamate se si verificano il timeout e se la persona del telefono sente la musica durante il parcheggio. È anche possibile specificare il file musicale da riprodurre mentre la chiamata è in attesa.
  
> [!NOTE]
> I file musicali personalizzati per il parcheggio delle chiamate non vengono sottoposto a backup come parte del processo di ripristino di emergenza di Skype for Business Server e andranno perduti se i file caricati nel pool sono danneggiati, danneggiati o eliminati. Mantieni sempre una copia di backup separata dei file personalizzati di musica in attesa caricati per Call Park. 
  
L'applicazione Call Park è un componente di Enterprise Voice. Quando si distribuisce VoIP aziendale, l'applicazione Call Park viene installata e attivata automaticamente. Prima di poter usare Call Park, tuttavia, l'amministratore di VoIP aziendale deve configurarlo e abilitarlo per gli utenti tramite il criterio vocale.
  
## <a name="deployment-and-requirements"></a>Distribuzione e requisiti

L'applicazione Call Park viene automaticamente installata quando si distribuisce VoIP aziendale. Si Abilita il parcheggio delle chiamate configurando il criterio vocale.
  
### <a name="software-requirements"></a>Requisiti software

Tutti i server front-end e i server Standard Edition in cui è distribuito Call Park devono avere installato Windows Media Format Runtime per i server che utilizzano Windows Server 2008 R2 o Microsoft Media Foundation per i server che utilizzano Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows. Windows Media Format Runtime o Microsoft Media Foundation è necessario per i file di Windows Media Audio (con estensione WMA) che chiamano Play Park per la musica in attesa.
  
### <a name="port-requirements"></a>Requisiti della porta

L'applicazione Call Park USA la **porta 5075** per le richieste di ascolto SIP.
    
> [!NOTE]
> Questa porta è un'impostazione predefinita che puoi modificare usando il cmdlet **Set-CsApplicationServer** . Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.
  
### <a name="audio-file-requirements"></a>Requisiti per i file audio

L'applicazione Call Park supporta solo file con estensione WMA (Windows Media Audio) per la musica in attesa. È possibile usare Microsoft Expression Encoder 4 per personalizzare i file per la musica in attesa. Per scaricare Expression Encoder 4, vedere ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843). Usare lo strumento per convertire il file in un formato WMA. Il formato consigliato per i file musicali di Call Park-in-blocco è l'audio multimediale 9, 44 kHz, 16 bit, mono, CBR, 32 kbps.
  
> [!NOTE]
> Il file convertito viene riprodotto al telefono solo a 16 kHz, anche se è stato registrato in 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Client e chiamate supportati

I client e i tipi di chiamate seguenti sono supportati per Call Park
  
### <a name="clients-supported-for-parking-calls"></a>Client supportati per le chiamate di parcheggio

Le chiamate da qualsiasi IP, PBX (Private Branch Exchange), PSTN (Public Switched Telephone Network) o cellulare possono essere parcheggiate.
  
> [!NOTE]
> Solo le chiamate audio possono essere parcheggiate. I messaggi istantanei e le conferenze non possono essere parcheggiati. 
  
I client seguenti possono usare Call Park per parcheggiare le chiamate:
  
- Skype for business
    
- Lync 2013
    
- Lync 2010
    
- Assistente di Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> I telefoni cellulari non possono usare Call Park per parcheggiare le chiamate. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Client supportati per il recupero delle chiamate

Gli intervalli di Orbit sono configurati come blocchi di estensioni virtuali (estensioni senza un utente o un telefono assegnato). Quando si configurano le orbite come estensioni virtuali, i telefoni cellulari e i telefoni PSTN non possono recuperare chiamate parcheggiate.
  
Gli utenti federati non possono recuperare chiamate parcheggiate.
  
I client seguenti possono recuperare le chiamate parcheggiate su Call Park:
  
- Skype for business
    
- Lync 2013
    
- Lync 2010
    
- Assistente di Lync 2010
    
- Lync Phone Edition
    
- Telefoni di area comune IP
    
- Telefoni non IP connessi all'infrastruttura di Skype for Business Server, inclusi i telefoni delle aree comuni e i telefoni PBX (Private Branch Exchange)
    
## <a name="call-park-capacity-planning"></a>Pianificazione della capacità di Call Park

La tabella seguente descrive il modello utente di Call Park che puoi usare come base per i requisiti di pianificazione della capacità.
  
> [!IMPORTANT]
> Tieni presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per i servizi di Call Park in entrambi i pool. 
  
**Modello utente di Call Park**

|**Metrica**|**Per pool <br/> front-end (con 8 server front-end)**|**Per server Standard Edition**|
|:-----|:-----|:-----|
|Tasso di parcheggio  <br/> |8 al minuto  <br/> |1 al minuto  <br/> |
|Recuperare la frequenza delle chiamate parcheggiate  <br/> |8 al minuto  <br/> |1 al minuto  <br/> |
|Durata media del parco  <br/> |60 secondi  <br/> |60 secondi  <br/> |
   

