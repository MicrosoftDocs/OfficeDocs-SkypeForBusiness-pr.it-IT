---
title: "Quali sono plan di messaggistica unificata?"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
description: "Learn what type of dial calling plans (PSTN Calling dial plans) are available with Office 365 and how to choose one for your company.  "
---

# Quali sono plan di messaggistica unificata?

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b). 
  
Un piano di chiamata è un insieme denominato di regole di normalizzazione che traducono i numeri di telefono composti da un singolo utente in un formato alternativo (in genere E.164) per l'autorizzazione delle chiamate e l'instradamento delle chiamate.
  
Un dial plan è costituito da uno o più regole di normalizzazione che definiscono come numeri di telefono espressi in vari formati vengono convertiti in un formato alternativo. La stessa stringa di connessione può essere interpretata e convertita in modo diverso nelle diverse plan di messaggistica unificata, in modo a seconda di quale plan di messaggistica unificata è assegnata a un determinato utente, lo stesso composto numero può essere convertito e inviato in modo leggermente diverso.
  
Vedere [Creare e gestire i dial plan](create-and-manage-dial-plans.md) per creare e gestire tenant plan di messaggistica unificata.
  
## Ambito tenant del piano di chiamata

Ambito di un dial plan determina il livello della gerarchia in cui può essere applicato il dial plan. Gli ambiti sono diversi da quella in Skype for Business Server 2015 locale distribuzione. I clienti ottengono al appropriato dial plan tramite il provisioning di impostazioni che sono fornite automaticamente quando gli utenti accedono a Skype for Business Online. Un amministratore, è possibile gestire e assegnare livelli di ambito dial plan tramite PowerShell remota.
  
In Skype for Business Online, sono disponibili due tipi di plan di messaggistica unificata-servizio nell'ambito e tenant, ovvero per l'organizzazione, nell'ambito. Un dial plan servizio nell'ambito è definito per ogni paese/area geografica in cui il sistema telefonico di Office 365 è disponibile. Ogni utente viene assegnato automaticamente il dial plan paese servizio corrispondente località di utilizzo Office 365 assegnate all'utente. Non è possibile modificare il servizio paese dial plan, ma è possibile creare tenant nell'ambito plan di messaggistica unificata, che migliorare il servizio paese dial plan. Come vengono effettuato il provisioning client, ottengono un "efficace dial plan," quale è una combinazione di servizio paese dial plan e il dial plan in modo appropriato ambito tenant. Non è quindi necessario definire tutte le regole di normalizzazione nel tenant plan di messaggistica unificata possono già esistenti nel servizio paese dial plan.
  
I piani di chiamata tenant si possono suddividere ulteriormente in due ambiti: l'ambito tenant e l'ambito utente. Se un tenant definisce e assegna un piano di chiamata con ambito utente, quell'utente riceverà in provisioning un piano di chiamata effettivo costituito dal piano di chiamata di servizio del Paese dell'utente e dal piano di chiamata assegnato all'utente. Se un tenant definisce un piano di chiamata con ambito tenant ma non assegna un piano di chiamata con ambito utente, quell'utente riceverà in provisioning un piano di chiamata effettivo costituito dal piano di chiamata di servizio del Paese e dal piano di chiamata tenant.
  
Quello che segue è il modello di ereditarietà dei piani di chiamata in Skype for Business online.
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
Di seguito sono riportati i possibili piani di chiamata effettivi.
  
 **Paese di servizio** Se non viene definito alcun dial plan tenant nell'ambito e alcun dial plan utente nell'ambito tenant non sono state assegnate all'utente di provisioning, l'utente riceverà un efficace dial plan mappati nel paese di servizio associato con il relativo percorso l'uso di Office 365.
  
 **Tenant globale: servizio paese** Se un dial plan utente tenant è definito ma non assegnati a un utente, l'utente provisioning verrà visualizzato un efficace dial plan costituita da un dial plan tenant unite e il dial plan paese servizio associato con il relativo percorso l'uso di Office 365.
  
 **Utente tenant: servizio paese** Se un dial plan utente tenant è definito e assegnato a un utente, l'utente provisioning verrà visualizzato un efficace dial plan costituito il dial plan utente tenant unite e il dial plan paese servizio associato con il relativo percorso l'uso di Office 365.
  
Vedere [Creare e gestire i dial plan](create-and-manage-dial-plans.md) per creare il tenant plan di messaggistica unificata.
  
## Pianificazione dei piani di chiamata tenant

Per pianificare piani di chiamata personalizzati, attenersi alla seguente procedura.
  
- **Passaggio 1** Decidere se personalizzato comporre piano è necessaria per ottimizzare l'utente esperienza di composizione. In genere, la necessità di uno, è possibile supportare composizione non e. 164, ad esempio le estensioni o abbreviato composizione nazionale.
    
- **Passaggio 2** Determinare se sono necessarie tenant globali o tenant utente nell'ambito dial plan oppure entrambi. Se gli utenti hanno esigenze di composizione locale diverso, sono necessari utente nell'ambito plan di messaggistica unificata.
    
- **Passo 3** Identificare i modelli di numerazione validi per ciascun piano di chiamata richiesto. Sono richiesti solo i modelli di numerazione che non sono definiti nel piano di chiamata di ambito di servizio del Paese.
    
- **Passo 4** Sviluppare un sistema a livello di organizzazione per la denominazione dei piani di chiamata. L'adozione di uno schema di denominazione standard assicura la coerenza in tutta l'organizzazione e rende più semplici la manutenzione e gli aggiornamenti.
    
[FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) ha risorse aggiuntive e i partner che possono risultare utili per l'implementazione di tenant dial plan.
  
## Creazione di un nuovo piano di chiamata di ambito tenant

Quando si crea un nuovo piano di chiamata, è necessario mettere le informazioni richieste.
  
### Nome e nome semplice

Per utente plan di messaggistica unificata, è necessario specificare un nome descrittivo che identifica agli utenti il dial plan verrà assegnato. Il dial plan nome semplice è prepopolato dei nomi con una stringa che dipende dal nome del piano di connessione. Il campo nome semplice è modificabile, che consente di creare una convenzione di denominazione più descrittiva per il dial plan. Il valore di nome semplice non può essere vuoto e deve essere univoco. Procedura consigliata consiste nel sviluppare una convenzione di denominazione per l'intera organizzazione e quindi utilizzare questa convenzione in modo coerente in tutti i siti e utenti.
  
### Descrizione

Consigliamo di digitare il nome comune riconoscibile della posizione geografica o del gruppo di utenti a cui si applica il piano di chiamata corrispondente. 
  
### Prefisso di accesso esterno

> [!CAUTION]
> Il prefisso di accesso esterno non è supportato al momento. 
  
È possibile specificare un prefisso di accesso esterno di un massimo di quattro caratteri (#, * e 0-9), se gli utenti hanno bisogno di comporre una o più cifre iniziali (ad esempio 9) per accedere alla linea esterna.
  
> [!NOTE]
> Se si specifica un prefisso di accesso esterno, non è necessario creare un'ulteriore regola di normalizzazione che comprenda il prefisso. 
  
Vedere [Creare e gestire i dial plan](create-and-manage-dial-plans.md) per creare il tenant plan di messaggistica unificata.
  
## Regole di normalizzazione

Le regole di normalizzazione definiscono come i numeri di telefono espressi in vari formati devono essere convertiti. La stessa stringa numerica può essere interpretata e tradotta in modo diverso, a seconda della posizione da cui viene composta. Le regole di normalizzazione possono essere necessarie se gli utenti devono essere in grado di comporre numeri interni o esterni abbreviati.
  
Uno o più regole di normalizzazione devono essere assegnate al dial plan. Le regole di normalizzazione corrispondono dall'alto verso il basso, in modo che l'ordine in cui vengono visualizzati in un dial plan tenant è importante. Ad esempio, se un dial plan tenant include 10 regole di normalizzazione, la logica corrispondente numerica digitata verrà tentata inizia con la prima regola normalizzazione, se non è presente una corrispondenza quindi il secondo e così via. Se viene effettuata una corrispondenza, non c'è alcun basata in modo che corrispondano regole, definite tale regola viene utilizzata. In un dial plan tenant specificato può essere presente un massimo di 25 regole di normalizzazione.
  
### Determinare le regole di normalizzazione richieste

Dato che qualsiasi piano di chiamata tenant viene di fatto unito al piano di chiamata di servizio del Paese di un determinato utente, è probabile che le regole di normalizzazione del piano di chiamata di servizio di un Paese debbano essere valutate per determinare quali regole di normalizzazione sono necessarie nel piano di chiamata tenant. Il cmdlet **Get-CsEffectiveTenantDialPlan** può essere utilizzato per questo scopo. Il cmdlet prende l'identità dell'utente come parametro di input e restituisce tutte le regole di normalizzazione applicabili per l'utente.
  
### Creazione di regole di normalizzazione

Le regole di normalizzazione usano le espressioni regolari .NET Framework per specificare modelli numerici di abbinamento che il server utilizza per tradurre le stringhe di composizione in formato E.164 allo scopo di eseguire la ricerca inversa. Possono essere create regole di normalizzazione specificando l'espressione regolare per cercare l'abbinamento e la conversione da eseguire quando si trova l'abbinamento. Terminata l'operazione, è possibile immettere un numero di prova per verificare che la regola di normalizzazione funzioni come previsto.
  
Per informazioni dettagliate sull'uso di .NET Framework espressioni regolari, vedere [Espressioni regolari di .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
Vedere [Creare e gestire i dial plan](create-and-manage-dial-plans.md) per creare e gestire normalizzazione regole per il tenant dial plan.
  
### Esempio di regole di normalizzazione

La tabella seguente mostra esempi di regole di normalizzazione scritte sotto forma di espressioni regolari .NET Framework. Si tratta solo di esempi, non di regole fisse di riferimento per la creazione di regole di normalizzazione.
  
 **Regole di normalizzazione mediante espressioni regolari di .NET Framework**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Nome regola** <br/> |**Descrizione** <br/> |**Schema numerico** <br/> |**Conversione** <br/> |**Esempio** <br/> |
|4digitExtension  <br/> |Converte i numeri interni a 4 cifre.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 viene convertito in +14255550100  <br/> |
|5digitExtension  <br/> |Converte i numeri interni a 5 cifre.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 viene convertito in +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte i numeri a 7 cifre in numeri locali di Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 viene convertito in +14255550100  <br/> |
|RedmondOperator  <br/> |Converte 0 nel numero del centralino per Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 viene convertito in +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte i numeri con il prefisso in rete (6) e il codice di sede di Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 viene convertito in +14255550100  <br/> |
|5digitRange  <br/> |Converte i numeri interni a 5 cifre iniziando con l'intervallo di cifre da 3 a 7, limiti inclusi.  <br/> |^([3-7]\\d{4})$  <br/> |+142570$1  <br/> |54567 viene convertito in +14255554567  <br/> |
|PrefixAdded  <br/> |Aggiunge un prefisso internazionale prima di un numero a 9 cifre, con limitazioni sulla prima e terza cifra.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 viene convertito in 14255554567  <br/> |
|NoTranslation  <br/> |Abbinamento a 5 cifre senza conversione.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 viene convertito in 34567  <br/> |
   
 **Piano di chiamata Redmond basato sulle regole di normalizzazione sopra indicate.**
  
La tabella seguente illustra un piano di chiamata di esempio per Redmond, Washington, Stati Uniti, in base alle regole di normalizzazione indicate nella tabella precedente.
  
||
|:-----|
|**Piano di chiamata Redmond** <br/> |
|5digitExtension  <br/> |
|7digitcallingRedmond  <br/> |
|RedmondSitePrefix  <br/> |
|RedmondOperator  <br/> |
   
> [!NOTE]
> I nomi delle regole di normalizzazione mostrati nella tabella precedente non includono spazi, ma questa è solo una scelta. Il primo nome nella tabella, ad esempio, avrebbe potuto essere "5 digit extension" o "5-digit Extension" e sarebbe stato comunque valido. 
  
## Argomenti correlati

[Creare e gestire i dial plan](create-and-manage-dial-plans.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

