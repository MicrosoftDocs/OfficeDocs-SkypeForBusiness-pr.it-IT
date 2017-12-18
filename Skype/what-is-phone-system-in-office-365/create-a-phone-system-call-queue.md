---
title: "Creare una coda di chiamata sistema telefonico"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061

description: "Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. "
---

# Creare una coda di chiamata sistema telefonico

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Code chiamata di sistema telefonico includono messaggi di saluto utilizzato quando un utente accede a un numero di telefono per l'organizzazione, la possibilità di automaticamente mettere le chiamate in attesa e di ricerca per l'agente di chiamata disponibile successiva gestire la chiamata durante le persone che hanno chiamata ascoltare musica durante l'attesa. È possibile creare una chiamata di unica o più code per l'organizzazione.
  
Telefono sistema chiamata code possono fornire:
  
- Un saluto aziendale.
    
- Musica mentre le persone sono in attesa.
    
- Reindirizzamento delle chiamate per chiamare gli agenti in liste di distribuzione via mail e gruppi di sicurezza.
    
- Impostazioni per le dimensioni massime della coda di chiamata, i timeout e le opzioni di gestione delle chiamate.
    
Quando qualcuno chiama un numero di telefono configurato con una coda di chiamata, sente prima un saluto (se è configurato) e poi viene messo in coda e aspetta il successivo agente di chiamata disponibile. Il chiamante ascolterà la musica durante l'attesa, e le chiamate verranno inoltrate agli agenti di chiamata in ordine  *FIFO (First In, First Out - Primo arrivato, primo servito)*  .
  
Tutte le chiamate in attesa nella coda saranno distribuite utilizzando una modalità di instradamento operatore:
  
- La prima chiamata in coda viene segnalata a tutti gli agenti di chiamata allo stesso tempo.
    
    > [!NOTE]
    > Gli agenti di chiamata che sono **Non in linea** o hanno la presenza configurata su **Non disturbare** non saranno chiamati.
  
- Solo una notifica di chiamata in arrivo (per la chiamata in cima alla coda) per volta viene inviata agli agenti di chiamata.
    
- Una volta che un agente di chiamata accetta la chiamata, la prossima chiamata in arrivo in coda viene segnalata agli agenti di chiamata.
    
## Fase 1 - Attività iniziali

Per iniziare a utilizzare le code di chiamata, è importante ricordare quanto segue.
  
- L'organizzazione deve avere (almeno) una licenza Enterprise E3 più **Sistema telefonico** o una licenza E5 Enterprise. Il numero di licenze utente **Sistema telefonico** assegnati impatto il numero del servizio di numeri che è disponibile da utilizzare per code di chiamata. Il numero di code di chiamata che è consentito dipende il numero di licenze **Sistema telefonico** e **Conferenze Audio** assegnati all'interno dell'organizzazione. Per ulteriori informazioni sulle licenze, passare[Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Per reindirizzare le chiamate a utenti dell'organizzazione che sono Online, vengono deve avere una licenza di **Sistema telefonico** e abilitati per VoIP aziendale o Office 365 si chiama plan di messaggistica unificata. Vedere[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Per consentire per Enterprise Voice, è possibile utilizzare Windows PowerShell. Ad esempio eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per ulteriori informazioni sulla chiamata piani di Office 365, vedere [Cosa sono i Piani per le chiamate in Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) e[Piani di chiamata per Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)
    
    > [!NOTE]
    > Gli utenti ospitati localmente con Skype for Business Server 2015 e Lync Server 2013 e 2010 non sono supportati come agenti di coda di chiamata. 
  
- È possibile assegnare un numero a pagamento e i numeri di telefono del servizio gratuito ottenuto in **Skype for Business admin center** o di trasferire da un altro provider di Servizi sistema telefonico chiamare code. Per accedere e utilizzare numeri verdi assistenza, è necessario configurare le comunicazioni crediti. Inoltre, se si desidera coda chiamata per effettuare chiamate in uscita a un numero PSTN (invece di trasferire la chiamata a un utente), le chiamate PSTN in uscita vengono addebitate al minuto tramite crediti comunicazioni indipendentemente dal fatto che la chiamata in uscita a un numero telefonico o internazionali. Per eseguire questa operazione, vedere[Cosa sono i Crediti comunicazioni?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) e[Configurare i Crediti comunicazioni per la propria organizzazione](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
    > [!NOTE]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati a code di chiamata, ma solo numeri di telefono di servizio a pagamento o numeri verdi. 
  
- Quando si distribuisce le chiamate in arrivo da una coda di chiamata sistema telefonico, questi client sono supportati per gli agenti di chiamata:
    
  - Client desktop Skype for Business 2016 (versioni a 32 e 64 bit)
    
  - Client desktop Lync 2013 (versioni a 32 e 64 bit)
    
  - Tutti i modelli di telefoni IP supportati per Skype for Business online. Consulta [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype for Business Client (versione 16.8.196 e versioni successive)
    
  - Android Skype for Business Client (versione 6.16.0.9 e versioni successive)
    
  - iPhone Skype for Business Client (versione 6.16.0 e versioni successive)
    
  - iPad Skype for Business Client (versione 6.16.0 e versioni successive)
    
## Fase 2 - Ottenere o trasferire numeri di servizio a pagamento o a numero verde

Prima di creare e configurare le code di chiamata, è necessario ottenere o trasferire i numeri di servizio esistenti (a pagamento o numeri verdi). Una volta ottenuti i numeri di servizio, a pagamento o numeri verdi, verranno visualizzati nell' **interfaccia di amministrazione Skype for Business** > **Voce** > scheda **Numeri di telefono**, e il **Tipo di numero** indicato sarà elencato come **Servizio - Numero verde**. Per avere i numeri di servizio, consulta [Recupero di numeri di telefono di servizio Skype for Business](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) oppure, se desideri trasferire e il numero di servizio esistente, consulta[Trasferire i numeri di telefono a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se sei al di fuori degli Stati Uniti, non è possibile utilizzare l'interfaccia di amministrazione Skype for Business per ottenere i numeri di servizio. Procedi [Gestire i numeri di telefono per la propria organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per sapere cosa fare fuori dagli Stati Uniti.
  
## Fase 3 - Creare una nuova coda di chiamata

Nell' **interfaccia di amministrazione di Skype for Business**, fai clic su **Instradamento chiamate** > **Code di chiamata**, poi fai clic su **Aggiungi nuovo**.
  
### Imposta il nome visualizzato della coda di chiamata, il numero di telefono e il dominio (se presente)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Nome** Immetti un nome visualizzato descrittivo per la coda di chiamata. È obbligatorio e può contenere fino a 64 caratteri, spazi inclusi. <br/> Questo nome verrà visualizzato nella notifica per la chiamata in arrivo.  <br/> |
|**2** <br/> |**Numero di telefono** Scegli un numero di servizio (a pagamento o numero verde) per la coda di chiamata. È obbligatorio. <br/> Se non ci sono numeri in elenco, devi ottenere numeri di servizio prima di poter creare questa coda di chiamata. Per ottenere questi numeri, vedi [Recupero di numeri di telefono di servizio Skype for Business](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md).  <br/> |
|**3** <br/> |**Dominio** Se è disponibile, scegli il dominio di Office 365 che desideri utilizzare. Questa opzione è disponibile solo se disponi di più di un dominio utilizzato con Office 365. Se ne hai più di uno, devi scegliere il nome di dominio dall'elenco. <br/> Ad esempio, puoi avere un dominio come:  _contoso.com or redmond.contoso.com_ <br/> |
   
### Impostare il saluto e la musica durante l'attesa

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
|||
|:-----|:-----|
|**1** <br/> |Il **Saluto** è opzionale. Questa è la musica riprodotta per i chiamanti in attesa nella coda di chiamata. <br/> Puoi caricare un file audio (in formato .wav, .mp3 o .wma).  <br/> |
|**2** <br/> |**Musica di attesa** Puoi utilizzare la musica di attesa predefinita fornita con la coda di chiamata, oppure caricare un file audio in formato .wav, .wma o .mp3 da utilizzare come musica di attesa personalizzata. <br/> |
   
### Aggiungere agenti di chiamata a una coda di chiamata

![Set up call queues.](../images/9c0c551b-218b-4268-9b73-c85000c99296.png)
  
|||
|:-----|:-----|
|**1** <br/> | Gli agenti di chiamata (50 al massimo) possono essere: <br/>  Un utente in linea con una licenza di **Sistema telefonico** e abilitato per VoIP aziendale o un piano di chiamata. <br/> > [!NOTE]>  Per reindirizzare le chiamate a utenti dell'organizzazione che sono Online, vengono deve avere una licenza di **Sistema telefonico** e abilitati per VoIP aziendale o un piano di chiamata. Vedere[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Per consentire per Enterprise Voice, è possibile utilizzare Windows PowerShell. Ad esempio eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`           Gli utenti in linea con una con una licenza di **Sistema telefonico** o una chiamata prevede che vengono aggiunti a una lista di distribuzione o un gruppo di sicurezza abilitati alla posta elettronica. Può richiedere fino a 30 minuti per un nuovo agente aggiunto per una lista di distribuzione o un gruppo di sicurezza per avviare la ricezione di chiamate da una coda di chiamata. Un gruppo di sicurezza o elenco di distribuzione appena creato potrebbe richiedere fino a 48 ore diventi disponibile per l'uso con code di chiamata. <br/> > [!NOTE]>  Gruppi di Office 365 (gruppi moderno) non possono essere utilizzati con code di chiamata.          > [!NOTE]>  Gli utenti ospitati localmente con Skype for Business Server 2015 e Lync Server 2013 e 2010 non sono supportati.          |
   
### Impostare la dimensione massima della coda e il tempo massimo di attesa

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Chiamate massime in coda** Consente di impostare il numero massimo di chiamate che possono aspettare in coda contemporaneamente. Il valore predefinito è 50 ma può variare da 0 a 200. <br/> Quando viene raggiunto questo limite, la chiamata verrà gestita nel modo definito dall'impostazione **Quando viene raggiunto il numero massimo di chiamate**, di seguito.  <br/> |
|**2** <br/> |**Quando viene raggiunto il numero massimo di chiamate** Quando la coda di chiamata raggiunge la sua dimensione massima (definita dall'impostazione **Chiamate massime in coda**) puoi scegliere cosa accade alle nuove chiamate in arrivo.  <br/> **Disconnetti con segnale di occupato** La chiamata verrà disconnessa. <br/> **Inoltra a** Quando scegli questa voce avrai le seguenti opzioni: <br/> **Persona della società** Un utente in linea con una licenza di **Sistema telefonico** e abilitato per VoIP aziendale o un piano di chiamata. È possibile impostare il in modo che la persona chiamata in può essere inviata alla segreteria telefonica. A tale scopo, selezionare una **persona dell'azienda** e questa persona avranno le chiamate inoltro delle chiamate direttamente alla segreteria telefonica. <br/> > [!NOTE]>  Gli utenti ospitati localmente con Skype for Business Server 2015 e Lync Server 2013 e 2010 non sono supportati.          **Coda di chiamata** Devi avere già creato un'altra coda di chiamata, ma dopo averlo fatto puoi selezionare quella coda di chiamata. <br/> **Operatore automatico** È necessario avere già creato un operatore automatico, ma dopo aver eseguito, è possibile selezionare l'operatore automatico. Vedere[Impostare un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).  <br/> |
|**3** <br/> |**Quanto tempo può aspettare una chiamata in coda** Puoi anche decidere quanto tempo una chiamata può restare in attesa in coda prima che vada in timeout e debba essere reindirizzata o scollegata. La destinazione è basata sull'impostazione **Quando una chiamata va in timeout**. Puoi impostare un tempo da 0 a 45 minuti.  <br/> |
|**4** <br/> |**Quando una chiamata va in timeout** Quando la chiamata raggiunge il limite impostato nell'impostazione **Quanto tempo può aspettare una chiamata in coda**, puoi scegliere cosa succede alla chiamata:  <br/> **Disconnetti** La chiamata verrà disconnessa. <br/> **Inoltra a** Quando scegli questa voce avrai le seguenti opzioni: <br/> **Persona della società** Un utente in linea con una licenza di **Sistema telefonico** e abilitato per VoIP aziendale o la chiamata plan di messaggistica unificata. È possibile impostare il in modo che la persona chiamata in può essere inviata alla segreteria telefonica. A tale scopo, selezionare una **persona dell'azienda** e questa persona avranno le chiamate inoltro delle chiamate direttamente alla segreteria telefonica. <br/> > [!NOTE]>  Gli utenti ospitati localmente con Skype for Business Server 2015 e Lync Server 2013 e 2010 non sono supportati.          **Coda di chiamata** Devi avere già creato un'altra coda di chiamata, ma dopo averlo fatto puoi selezionare quella coda di chiamata. <br/> **Operatore automatico** È necessario avere già creato un operatore automatico, ma dopo aver eseguito, è possibile selezionare l'operatore automatico. Vedere[Impostare un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).  <br/> |
   
## Modificare l'ID chiamante dell'utente per diventare un numero di telefono di una chiamata coda

È possibile proteggere identità dell'utente modificando il loro ID chiamante per le chiamate in uscita a una coda di chiamata invece mediante la creazione di un criterio utilizzando il cmdlet **New-CallingLineIdentity**.
  
Per eseguire quest'esecuzione:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Quindi applicare i criteri per l'utente utilizzando il cmdlet **Grant-CallingLineIdentity**. Per eseguire quest'esecuzione:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

È possibile ottenere altre informazioni su come modificare le impostazioni di ID chiamante nell'organizzazione [Come usare l'ID chiamante nella tua organizzazione](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## Per saperne di più

Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.
  
### Cmdlet della coda di chiamata

Questi sono i cmdlet necessari per gestire una coda di chiamata.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### Altre informazioni su Windows PowerShell

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

