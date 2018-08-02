---
title: Creare una coda di chiamata del Sistema telefonico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 9b86bec84846dff36e509488eb34f0415fe8cd95
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2018
ms.locfileid: "21708351"
---
# <a name="create-a-phone-system-call-queue"></a>Creare una coda di chiamata del Sistema telefonico

Chiamata al sistema telefonico code includono messaggi di saluto che vengono utilizzati quando si riceve una chiamata a un numero di telefono per l'organizzazione, la possibilità di inserire automaticamente le chiamate in attesa e le funzionalità di ricerca per il successivo agente disponibile chiamata gestire la chiamata mentre gli utenti che chiamata in attesa la musica di attesa. È possibile creare uno o più code di chiamata per l'organizzazione.
  
Chiamata al sistema possono fornire le code del telefono:
  
- Un saluto aziendale.
    
- Musica mentre le persone sono in attesa.
    
- Reindirizzamento delle chiamate per chiamare agenti in gruppi di protezione e le liste di distribuzione abilitati alla posta elettronica.
    
- Configurare le impostazioni per la dimensione massima della coda di chiamata, timeout e le opzioni di gestione delle chiamate.
    
Quando si riceve una chiamata a un numero di telefono che viene impostato di backup con una coda di chiamata verrà sentire un messaggio di saluto principale (se una configurazione), quindi verrà inserito in coda e attendere il successivo agente disponibile chiamata. Il chiamante ascolterà la musica durante l'attesa, e le chiamate verranno inoltrate agli agenti di chiamata in ordine  *FIFO (First In, First Out - Primo arrivato, primo servito)*  .
  
Tutte le chiamate in attesa nella coda verranno distribuite tramite una modalità routing operatore oppure la modalità di routing seriale:
  
- Con l'operatore di routing, la prima chiamata nella coda deve squillare tutti gli agenti contemporaneamente.
    
- Con il routing seriale, la chiamata prima della coda deve squillare tutti gli agenti di chiamata uno alla volta.
    
    > [!NOTE]
    > Non verranno chiamati agli agenti chiamata sono **non in linea**, aver impostato la presenza su **non disturbare,** oppure sono stato scelto nella coda di chiamata.
  
- Solo una notifica di chiamata in arrivo (per la chiamata in cima alla coda) per volta viene inviata agli agenti di chiamata.
    
- Una volta che un agente di chiamata accetta la chiamata, la prossima chiamata in arrivo in coda viene segnalata agli agenti di chiamata.
    
## <a name="step-1---getting-started"></a>Fase 1 - Attività iniziali

Per iniziare a utilizzare le code di chiamata, è importante ricordare quanto segue.
  
- L'organizzazione deve disporre (almeno) una licenza Enterprise E3 plus **Sistema telefonico** o una licenza Enterprise E5. Il numero di licenze utente **Sistema telefonico** assegnati influisce sul numero dei numeri di servizio disponibili essere utilizzati per le code di chiamata. Il numero di code di chiamata che è possibile avere dipende il numero di licenze **Sistema telefonico** e **Audioconferenza** assegnati all'interno dell'organizzazione. Per ulteriori informazioni sulle licenze, Vai [qui](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Per reindirizzare le chiamate agli utenti dell'organizzazione che sono in linea, che deve disporre di una licenza di **Sistema telefonico** e abilitati per Enterprise Voice o dispone prevede la chiamata di Office 365. Vedere [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell. Ad esempio, eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per ulteriori informazioni sui piani di chiamata di Office 365, vedere [che cosa sono i piani di chiamata in Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) e [La chiamata a piani per Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati come un agenti di coda di chiamata. 
  
- È possibile assegnare solo a pagamento e numeri di telefono verdi servizio anche in **Skype per interfaccia di amministrazione di Business** o trasferite da un altro provider di servizi a code chiamata sistema telefonico. Per ottenere e utilizzare numeri verdi assistenza, è necessario impostare i titoli di coda di comunicazioni.
    
    > [!NOTE]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati a code di chiamata, ma solo numeri di telefono di servizio a pagamento o numeri verdi. 
  
- Quando si distribuiscono le chiamate in arrivo dalla coda di chiamata di un sistema telefonico, questi client sono supportati per gli agenti di chiamata:
    
  - Client desktop Skype for Business 2016 (versioni a 32 e 64 bit)
    
  - Client desktop Lync 2013 (versioni a 32 e 64 bit)
    
  - Tutti i modelli di telefoni IP supportati per Skype for Business online. Vedere [Getting telefoni Skype Business online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Skype Mac di Client Business (versione 16.8.196 e versioni successive) 
    
  - Android Skype per Client Business (versione 6.16.0.9 e versioni successive)
    
  - iPhone Skype per Client Business (versione 6.16.0 e versioni successive)
    
  - iPad Skype per Client Business (versione 6.16.0 e versioni successive)

  - Client Microsoft team Windows (versioni a 32 e 64 bit)

  - Client Microsoft Team Mac

  - Microsoft Teams iPhone app

  - Team di Microsoft app Android
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Fase 2 - Ottenere o trasferire numeri di servizio a pagamento o a numero verde

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. Dopo aver ottenuto il numero a tariffa o numeri verdi servizio, che verranno visualizzati nella **Skype per Business admin center** > **vocale** > **numeri di telefono**e **tipo di numero** elencato verrà indicato come **servizio - numero verde **. Per ottenere i numeri di servizio, vedere [Getting numeri di telefono del servizio per Skype per le aziende e team Microsoft che](getting-service-phone-numbers.md) oppure se si desidera trasferimento e il numero di servizio esistente, [trasferire i numeri di telefono a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se si è fuori degli Stati Uniti, è possibile utilizzare Skype per interfaccia di amministrazione di Business per ottenere i numeri di servizio. Vai a [Gestisci i numeri di telefono per l'organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) ma per informazioni su come effettuare di fuori degli Stati Uniti.
  
## <a name="step-3---create-a-new-call-queue"></a>Fase 3 - Creare una nuova coda di chiamata

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**

Nell' **interfaccia di amministrazione di Skype for Business**, fai clic su **Instradamento chiamate** > **Code di chiamata**, poi fai clic su **Aggiungi nuovo**.
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Imposta il nome visualizzato della coda di chiamata, il numero di telefono e il dominio (se presente)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Numero 1](../images/sfbcallout1.png)<br/>
**Nome** Immetti un nome visualizzato descrittivo per la coda di chiamata. È obbligatorio e può contenere fino a 64 caratteri, spazi inclusi.<br/> Questo nome verrà visualizzato nella notifica per la chiamata in arrivo.
***
![Numero 2](../images/sfbcallout2.png)<br/>**Numero di telefono** Scegli un numero di servizio (a pagamento o numero verde) per la coda di chiamata. Ciò è facoltativa. <br/> Se non ci sono numeri in elenco, devi ottenere numeri di servizio prima di poter creare questa coda di chiamata. Per ottenere i numeri di servizio, vedere [Getting numeri di telefono del servizio per Skype per le aziende e team di Microsoft](getting-service-phone-numbers.md)
***
![Numero 3](../images/sfbcallout3.png)<br/>**Dominio** Se è disponibile, scegli il dominio di Office 365 che desideri utilizzare. Questa opzione è disponibile solo se disponi di più di un dominio utilizzato con Office 365. Se ne hai più di uno, devi scegliere il nome di dominio dall'elenco.<br/> Ad esempio, puoi avere un dominio come:  _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Impostare il saluto e la musica durante l'attesa

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>Il **Saluto** è opzionale. Questo è il messaggio di saluto riprodotto per gli utenti che chiamano per il numero di coda di chiamata. <br/> È possibile caricare un file audio (formati. wav, MP3 o. wma).
***
![Numero 2](../images/sfbcallout2.png)<br/>**Musica di attesa** È possibile utilizzare l'impostazione predefinita, la musica di attesa fornita con la coda chiamata oppure è possibile caricare un file audio nel formato con estensione wav, mp3 o. wma da utilizzare come musica personalizzata in attesa. 
   

### <a name="select-the-call-distribution-method"></a>Selezionare il metodo di distribuzione di chiamata

![Vengono illustrate le chiamate opzioni metodo di distribuzione](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>**Chiamare il metodo di distribuzione** È possibile scegliere **operatore** o **seriale** per il metodo di distribuzione della coda di chiamata. Tutte le code di chiamata nuovi ed esistenti hanno routing operatore selezionata per impostazione predefinita. Per utilizzare il routing seriale, è necessario scegliere l'opzione di routing **seriale** in modo esplicito nell'interfaccia utente e i cmdlet. <br/><br/> Quando si sceglie il routing seriale e viene salvata la coda di chiamata, le chiamate dalla coda squillerà gli agenti uno alla volta, a partire dall'inizio dell'elenco di agenti. Se un agente Elimina o non seleziona una chiamata, la chiamata squillerà agente successivo nell'elenco e cercherà tutti gli agenti uno alla volta fino a quando non si è prelevato o timeout in attesa nella coda.   

> [!NOTE]
> Il routing seriale ignorerà gli agenti di persone **non in linea**, aver impostato la presenza su **non disturbare**o **scelto** di ricevere chiamate da questa coda. 
   
### <a name="select-an-agent-opt-out-option"></a>Selezionare un agente esplicito opzione

![Casella di controllo Mostra l'agente esplicito](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>**Agente esplicito opzione** È possibile scegliere di consentire agli agenti coda di chiamata disattivare taking le chiamate provenienti da una coda particolare selezionando **l'Opzione esplicito agente**.  <br/> Attivando questa opzione consente a tutti gli agenti nella coda per avviare o interrompere la ricezione di chiamate da questa coda chiamata al verranno. È possibile revocare il privilegio con consenso esplicito alla partecipazione dell'agente in qualsiasi momento, deselezionare la casella di controllo, causando agenti diventare automaticamente incluso per questa coda nuovamente (impostazione predefinita per tutti gli agenti).  <br/><br/> Per accedere all'opzione di esclusione, gli agenti possono eseguire le operazioni seguenti:
 1. Aprire **le opzioni** nel proprio desktop Skype per client di Business. 
 2. Nella scheda **Inoltro** di chiamata, fare clic sul collegamento **Modifica impostazioni online** .
 3. Nella pagina Impostazioni utente, fare clic su **Chiama code**e quindi deselezionare le caselle di controllo per una o più code per cui desiderano consentire in modo esplicito.
 
    > [!NOTE] 
    > Agenti tramite Mac, mobile o client Lync 2013 o Hybrid Voice utenti ospitati locale con Skype per 2015 Business server, è possibile accedere ai [https://aka.ms/cqsettings](https://aka.ms/cqsettings) per accedere a consenso esplicito opzione out.
   
### <a name="add-call-agents-to-a-call-queue"></a>Aggiungere agenti di chiamata a una coda di chiamata

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/><br/>Gli agenti di chiamata (50 massimo) possono essere:
*    Un utente in linea con una licenza di **Sistema telefonico** e abilitato per Enterprise Voice o con un piano di chiamata. <br/><br/> **Nota:**  Per reindirizzare le chiamate agli utenti dell'organizzazione che sono in linea, che deve disporre di una licenza di **Sistema telefonico** e abilitati per Enterprise Voice o disporre di un piano di chiamata. Vedere [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell. Ad esempio, eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Utenti in linea con una licenza di **Sistema telefonico** e un piano di chiamata che vengono aggiunti a un gruppo di Office 365, una lista di distribuzione abilitati alla posta elettronica o un gruppo di sicurezza. Possono occorrere fino a 30 minuti perché un nuovo agente aggiunto a una lista di distribuzione o gruppo di sicurezza inizi a ricevere chiamate da una coda di chiamata. Un gruppo di sicurezza o elenco distribuzione appena creata può richiedere fino a 48 ore per diventare disponibili per l'utilizzo con le code di chiamata. Appena creati gruppi di Office 365 sono disponibili quasi immediatamente. <br/> 

    > [!NOTE] 
    > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Impostare la dimensione massima della coda e il tempo massimo di attesa

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/><br/>**Chiamate massime in coda** Consente di impostare il numero massimo di chiamate che possono aspettare in coda contemporaneamente. Il valore predefinito è 50, ma compreso tra 0 e 200. quando tale limite viene raggiunto, la chiamata verrà gestita in modo impostate sull'impostazione **quando viene raggiunto il numero massimo di chiamate** .
***
![Numero 2](../images/sfbcallout2.png)<br/><br/>**Quando viene raggiunto il numero massimo di chiamate** Quando la coda di chiamate raggiunge la dimensione massima (impostata utilizzando l'impostazione **massimo chiama nella coda** ), è possibile scegliere cosa accade a nuove chiamate in arrivo.
*    **Disconnetti con segnale di occupato** La chiamata verrà disconnessa.
*    **Inoltrare la chiamata** Quando si sceglie questo, si disporrà di queste opzioni:
     *    **Persona nell'azienda** Un utente in linea con una licenza di **Sistema telefonico** e abilitato per Enterprise Voice o un piano di chiamata. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. A tale scopo, selezionare una **persona nell'azienda** e impostare tale persona per le chiamate inoltrate direttamente alla segreteria telefonica. <br/> <br/>Per ulteriori informazioni sulle licenze necessarie per la segreteria telefonica, vedere [impostare i messaggi vocali sistema telefonico](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 
     
        > [!Note]
        > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.<br/>
     
     *    **Coda di chiamata** È necessario avere già creato un'altra coda di chiamata, ma dopo aver eseguito, è possibile selezionare la coda di chiamata.
     *    **Operatore automatico** È necessario avere già creato un operatore automatico, ma dopo aver eseguito, è possibile selezionare tale operatore automatico. Vedere [configurare un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).
***
![Numero 3](../images/sfbcallout3.png)<br/><br/>**Quanto tempo può aspettare una chiamata in coda** Puoi anche decidere quanto tempo una chiamata può restare in attesa in coda prima che vada in timeout e debba essere reindirizzata o scollegata. La destinazione è basata sull'impostazione **Quando una chiamata va in timeout**. Puoi impostare un tempo da 0 a 45 minuti.  <br/><br/> Intervalli di 15 secondi, è possibile impostare il valore di timeout in secondi. In questo modo è possibile modificare il flusso delle chiamate con granularità maggiore. Ad esempio, è possibile specificare che tutte le chiamate non vengono affrontate da un agente entro 30 secondi passano a un operatore automatico di ricerca di Directory. 

***
![Numero 4](../images/sfbcallout4.png)<br/><br/>**Quando una chiamata va in timeout** Quando la chiamata raggiunge il limite impostato nell'impostazione **Quanto tempo può aspettare una chiamata in coda**, puoi scegliere cosa succede alla chiamata:
*    **Disconnetti** La chiamata verrà disconnessa.
*    **Inoltrare la chiamata** Quando si sceglie questo, si disporrà di queste opzioni:
     *    **Persona nell'azienda** Un utente in linea con una licenza di **Sistema telefonico** e abilitato per Enterprise Voice o piani di chiamata. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. A tale scopo, selezionare una **persona nell'azienda** e impostare tale persona per le chiamate inoltrate direttamente alla segreteria telefonica. </br><br/>  Per ulteriori informazioni sulle licenze necessarie per la segreteria telefonica, vedere [impostare i messaggi vocali sistema telefonico](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 

        > [!Note]
        > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.<br/>

     *    **Coda di chiamata** È necessario avere già creato un'altra coda di chiamata, ma dopo aver eseguito, è possibile selezionare la coda di chiamata.
     *    **Operatore automatico** È necessario avere già creato un operatore automatico, ma dopo aver eseguito, è possibile selezionare tale operatore automatico. Vedere [configurare un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modificare l'ID chiamante dell'utente sia il numero di telefono della coda di chiamata

È possibile proteggere l'identità dell'utente modificando l'ID chiamante per le chiamate in uscita a una coda di chiamata in realtà mediante la creazione di un criterio utilizzando il cmdlet **New-CallingLineIdentity** .
  
Per farlo, eseguire quanto segue:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Quindi applicare il criterio per utente utilizzando il cmdlet **Grant-CallingLineIdentity** . Per farlo, eseguire quanto segue:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

È possibile ottenere ulteriori informazioni su come apportare modifiche alle impostazioni di ID chiamante nell'organizzazione [di seguito](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Per saperne di più

Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.
  
### <a name="call-queue-cmdlets"></a>Cmdlet della coda di chiamata

Questi sono i cmdlet necessari per gestire una coda di chiamata.
  
- [Nuovo CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Altre informazioni su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Ecco cosa offre il Sistema telefonico in Office 365](here-s-what-you-get-with-phone-system.md)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 
