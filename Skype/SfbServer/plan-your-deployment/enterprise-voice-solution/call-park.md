---
title: Pianificare il parcheggio di chiamata in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 'Pianificazione del parcheggio di chiamata in Skype for Business Server VoIP aziendale, che consente di mettere le chiamate in attesa e trasferire le chiamate ai reparti. Include la pianificazione della capacità, le chiamate supportate e i client supportati.'
---

# <a name="plan-for-call-park-in-skype-for-business"></a>Pianificare il parcheggio di chiamata in Skype for Business
 
Pianificazione del parcheggio di chiamata in Skype for Business Server VoIP aziendale, che consente di mettere le chiamate in attesa e trasferire le chiamate ai reparti. Include la pianificazione della capacità, le chiamate supportate e i client supportati.
  
L'applicazione Parcheggio di chiamata consente VoIP aziendale utenti di eseguire le operazioni seguenti:
  
- Mettere una chiamata in attesa e quindi recuperare la chiamata dallo stesso telefono o da uno diverso.
    
- Mettere una chiamata in attesa per trasferirla a un altro reparto o a un'altra area generale, ad esempio a un reparto vendite o un magazzino in cui è presente un telefono di area comune.
    
- Mettere una chiamata in attesa e mantenere libero per altre chiamate il telefono originale da cui si è risposto alla chiamata.
    
Quando un utente parcheggia una chiamata, Skype for Business Server la trasferisce a un numero temporaneo, denominato orbit, in cui la chiamata viene mantenuta fino a quando non viene recuperata o si verifica il timeout. Skype for Business Server invia l'orbit all'utente che ha parcheggiato la chiamata. Per recuperare la chiamata parcheggiata, l'utente può comporre il codice orbit o fare clic sul collegamento o il pulsante del codice orbit nella finestra Conversazione. 
  
L'utente che ha eseguito il parcheggio di una chiamata può indicare a qualcun altro di recuperare la chiamata utilizzando un meccanismo esterno, ad esempio un sistema di messaggistica istantanea o di paging, per comunicare il codice orbit a un altro utente. L'utente che ha eseguito il parcheggio della chiamata può lasciare aperta la finestra Conversazione per ricevere una notifica quando la chiamata viene recuperata.
  
Poiché gli intervalli di codici orbit sono univoci a livello globale, è possibile recuperare le chiamate da qualsiasi Skype for Business Server o telefono PBX se il routing è configurato in modo appropriato. Se nessuno recupera la chiamata entro una quantità di tempo configurabile, la chiamata viene nuovamente indirizzata alla persona che ne ha eseguito il parcheggio. Se tale persona non risponde alla richiamata, la chiamata viene trasferita a una destinazione di fallback, ad esempio a un operatore, se questa impostazione è configurata. È possibile configurare da uno a dieci il numero di volte per cui consentire una richiamata prima che la chiamata venga trasferita. Se nessuno risponde a una chiamata trasferita, questa viene disconnessa. Il codice orbit viene liberato quando la chiamata viene recuperata o disconnessa.
  
Quando si distribuisce il parcheggio di chiamata, è necessario riservare intervalli di numeri di interno (codici orbit) per il parcheggio delle chiamate. Tali numeri devono essere interni virtuali, ovvero numeri a cui non sono assegnati utenti o telefoni. È quindi necessario configurare la tabella dei codici orbit del parcheggio di chiamata con gli intervalli di interni e specificare il servizio applicazione che ospita l'applicazione Parcheggio di chiamata che gestisce ogni intervallo. Ogni pool Front End include una tabella di parcheggio di chiamata nel server di back-end corrispondente utilizzato per gestire le chiamate parcheggiate nel pool. L'elenco degli intervalli di orbit viene archiviato nell'archivio di gestione centrale e viene utilizzato per instradare i orbit al pool di destinazione. Ogni Skype for Business Server pool in cui l'applicazione Parcheggio di chiamata viene distribuita e configurata può avere uno o più intervalli di orbit. Gli intervalli orbit devono essere univoci a livello globale nella Skype for Business Server distribuzione. 
  
È anche possibile configurare altre impostazioni di parcheggio chiamata, ad esempio la destinazione di reindirizzamento delle chiamate in caso di timeout e se usare la musica di attesa durante il parcheggio. È anche possibile specificare il file musicale da riprodurre mentre la chiamata è in attesa.
  
> [!NOTE]
> I file di musica di attesa personalizzati per Parcheggio di chiamata non vengono sottoposti a backup nell'ambito del processo di ripristino di emergenza di Skype for Business Server e andranno persi se i file caricati nel pool sono danneggiati, danneggiati o cancellati. Mantenere sempre una copia di backup distinta dei file di musica di attesa personalizzati caricati per il parcheggio chiamate. 
  
L'applicazione Parcheggio di chiamata è un componente di VoIP aziendale. Quando si distribuisce VoIP aziendale, l'applicazione Parcheggio di chiamata viene installata e attivata automaticamente. Prima di poter utilizzare l'applicazione Parcheggio di chiamata, tuttavia, l'amministratore di VoIP aziendale deve configurarla e abilitarla per gli utenti tramite criteri vocali.
  
## <a name="deployment-and-requirements"></a>Distribuzione e requisiti

L'applicazione Parcheggio di chiamata viene installata automaticamente quando si distribuisce VoIP aziendale. È possibile abilitare parcheggio di chiamata configurando i criteri vocali.
  
### <a name="software-requirements"></a>Requisiti software

Per tutti i Front End Server e i server edizione Standard in cui è distribuito Il parcheggio di chiamata deve essere installato Runtime formato multimediale di Windows per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte di Windows Desktop Experience. Windows Runtime formato multimediale o Microsoft Media Foundation è necessario per i file Windows Media Audio (wma) riprodotti da Parcheggio di chiamata per la musica in attesa.
  
### <a name="port-requirements"></a>Requisiti delle porte

L'applicazione Parcheggio di chiamata **utilizza la porta 5075 per**  le richieste di attesa SIP.
    
> [!NOTE]
> Questa porta è un'impostazione predefinita che può essere modificata usando il cmdlet **Set-CsApplicationServer**. Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Lync Server Management Shell.
  
### <a name="audio-file-requirements"></a>Requisiti dei file audio

L'applicazione Parcheggio di chiamata supporta solo Windows file Audio multimediale (wma) per la musica in attesa. Per personalizzare i file per la musica di attesa, è possibile usare Microsoft Expression Encoder 4. Per scaricare Expression Encoder 4, vedere   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843). Utilizzare lo strumento per convertire il file in un formato wma. Il formato consigliato per i file di musica di attesa del parcheggio di chiamata è Media Audio 9, 44 kHz, 16 bit, Mono, CBR, 32 kbps.
  
> [!NOTE]
> Il file convertito viene riprodotto nel telefono solo a 16 kHz, anche se è stato registrato a 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Client e chiamate supportati

I client e i tipi di chiamate seguenti sono supportati per parcheggio di chiamata
  
### <a name="clients-supported-for-parking-calls"></a>Client supportati per parcheggiare le chiamate

È possibile parcheggiare chiamate da qualsiasi telefono IP, PBX (Private Branch Exchange), PSTN (Public Switched Telephone Network) o cellulare.
  
> [!NOTE]
> Solo le chiamate audio possono essere parcheggiate. Questa funzionalità non è disponibile per messaggi istantanei e conferenze. 
  
I client seguenti possono utilizzare parcheggio di chiamata per parcheggiare le chiamate:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> I telefoni cellulari non possono usare Parcheggio di chiamata per parcheggiare le chiamate. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Client supportati per il recupero delle chiamate

Gli intervalli di codici orbit sono configurati come blocchi di estensioni virtuali, ovvero estensioni a cui non sono assegnati utenti o telefoni. Quando si configurano i codici orbit come estensioni virtuali, i telefoni cellulari e i telefoni PSTN non supportano il recupero delle chiamate parcheggiate.
  
Gli utenti federati non possono recuperare le chiamate parcheggiate.
  
I client seguenti possono recuperare le chiamate parcheggiate nel parcheggio di chiamata:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- Telefono IP di area comune
    
- Telefoni non IP connessi all'infrastruttura Skype for Business Server, inclusi telefoni di area comune e telefoni PBX (Private Branch Exchange)
    
## <a name="call-park-capacity-planning"></a>Pianificazione della capacità del parcheggio di chiamata

Nella tabella seguente viene descritto il modello utente parcheggio di chiamata che è possibile utilizzare come base per i requisiti di pianificazione della capacità.
  
> [!IMPORTANT]
> Tenere presente che, per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato deve essere in grado di gestire i carichi di lavoro per i servizi parcheggio di chiamata in entrambi i pool. 
  
**Modello utente del parcheggio di chiamata**

|**Metrica**|**Per pool  <br/>  Front End (con 8 Front End Server)**|**Per server Standard Edition**|
|:-----|:-----|:-----|
|Frequenza di parcheggio  <br/> |8 al minuto  <br/> |1 al minuto  <br/> |
|Frequenza di recupero delle chiamate parcheggiate  <br/> |8 al minuto  <br/> |1 al minuto  <br/> |
|Durata media del parcheggio  <br/> |60 secondi  <br/> |60 secondi  <br/> |
   

