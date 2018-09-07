---
title: Creare una coda di chiamata di Sistema telefonico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: "Informazioni su come configurare Sistema telefonico per le code di chiamata di Office 365 (Cloud PBX) per fornire un messaggio di saluto, una musica di attesa e per reindirizzare le chiamate ad agenti nelle liste di distribuzione e gruppi di protezione dell'organizzazione. È inoltre possibile impostare la dimensione massima della coda, il timeout e le opzioni di gestione delle chiamate. "
ms.openlocfilehash: bb9812eb880ce7451c2fd30f93fa080d6ec84c87
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854448"
---
# <a name="create-a-phone-system-call-queue"></a>Creare una coda di chiamata di Sistema telefonico

Le code di chiamata di Sistema telefonico includono messaggi di saluto che vengono utilizzati quando si riceve una chiamata a un numero di telefono aziendale, la possibilità di inserire automaticamente le chiamate in attesa e la funzionalità di ricerca per il successivo agente disponibile mentre gli utenti in attesa ascoltano una musica. Puoi creare una o più code di chiamata per l'organizzazione.
  
Le code di chiamata di Sistema possono fornire:
  
- Un saluto aziendale.
    
- Musica mentre le persone sono in attesa.
    
- Reindirizzamento delle chiamate per chiamare gli agenti in liste di distribuzione per posta elettronica e gruppi di protezione.
    
- Impostazioni per le dimensioni massime della coda di chiamata, il timeout e le opzioni di gestione delle chiamate.
    
Quando qualcuno chiama un numero di telefono configurato con una coda di chiamata, sente prima un saluto (se è configurato) e poi viene messo in coda e aspetta il successivo agente di chiamata disponibile. Il chiamante ascolterà la musica durante l'attesa, e le chiamate verranno inoltrate agli agenti di chiamata in ordine  *FIFO (First In, First Out - Primo arrivato, primo servito)*  .
  
Tutte le chiamate in attesa nella coda saranno distribuite utilizzando una modalità di instradamento operatore o seriale:
  
- Con l'instradamento operatore, la prima chiamata nella coda squillerà a tutti gli agenti contemporaneamente.
    
- Con l'instradamento seriale, la prima chiamata della squillerà a tutti gli agenti di chiamata uno alla volta.
    
    > [!NOTE]
    > Non verranno chiamati agli agenti chiamata che sono **Non in linea**, che hanno impostato la presenza su **Non disturbare,** oppure sono usciti dalla coda di chiamata.
  
- Solo una notifica di chiamata in arrivo (per la chiamata in cima alla coda) per volta viene inviata agli agenti di chiamata.
    
- Una volta che un agente di chiamata accetta la chiamata, la prossima chiamata in arrivo in coda viene segnalata agli agenti di chiamata.
    
## <a name="step-1---getting-started"></a>Fase 1 - Attività iniziali

Per iniziare a utilizzare le code di chiamata, è importante ricordare quanto segue:
  
- La propria organizzazione deve disporre (almeno) di una licenza Enterprise E3 plus con **Sistema telefonico** o una licenza Enterprise E5. Il numero di licenze utente di **Sistema telefonico** assegnate influisce sul numero dei numeri di servizio disponibili per gli operatori automatici. Il numero di code di chiamata che è possibile avere dipende dal numero di licenze **Sistema telefonico** e **Audioconferenza** assegnate all'interno dell'organizzazione. Per ulteriori informazioni sulle licenze, vai [qui](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Per reindirizzare le chiamate agli utenti dell'organizzazione che sono in linea, essi devono disporre di una licenza di **Sistema telefonico** ed essere abilitati per Enterprise Voice o avere Piani di chiamata di Office 365. Consulta [Assegnare le licenze per i componenti aggiuntivi di Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell. Ad esempio, esegui:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per ulteriori informazioni sui piani di chiamata di Office 365, consulta [Che cosa sono i Piani di chiamata in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)  e [Piani di chiamata per Office 365](/microsoftteams/calling-plans-for-office-365).
    
    > [!NOTE]
    > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati come agenti di coda di chiamata. 
  
- È possibile assegnare solo numeri telefonici di servizio a pagamento e gratuiti anche nell'**Interfaccia di amministrazione di Skype fpr Business** o trasferire da un altro provider di servizi a code di chiamata di Sistema telefonico. Per ottenere e utilizzare i numeri gratuiti, è necessario impostare il Credito per la comunicazione.
    
    > [!NOTE]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati a code di chiamata, ma solo numeri di telefono di servizio a pagamento o numeri verdi. 
  
- Quando si distribuiscono le chiamate in arrivo dalla coda di chiamata di un sistema telefonico, i successivi client sono supportati per gli agenti di chiamata:
    
  - Client desktop Skype for Business 2016 (versioni a 32 e 64 bit)
    
  - Client desktop Lync 2013 (versioni a 32 e 64 bit)
    
  - Tutti i modelli di telefoni IP supportati per Skype for Business online. Consulta [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Client Mac Skype for Business (versione 16.8.196 e versioni successive) 
    
  - Client Android Skype for Business (versione 6.16.0.9 e versioni successive)
    
  - Client iPhone Skype for Business (versione 6.16.0 e versioni successive)
    
  - Client Mac Skype for Business (versione 6.16.0 e versioni successive)

  - Client Microsoft Teams Windows (versioni a 32 e 64 bit)

  - Client Microsoft Teams Mac

  - Microsoft Teams iPhone app

  - Microsoft Teams Android app
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Passo 2 - Ottenere o trasferire numeri di servizio a pagamento o gratuiti

Prima di poter creare e configurare le code di chiamata, è necessario ottenere numeri di servizio a pagamento o meno oppure  trasferire quelli esistenti. Dopo aver ottenuto i numeri di servizio, a pagamento o meno, questi verranno visualizzati nell'interfaccia di amministrazione di **Skype per Business** > **Vocale** > **Numeri di telefono** e **Tipo di numero** elencato verrà indicato come **Servizio - numero verde**. Per ottenere i numeri di servizio, vedere [Ottenere numeri di telefono di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md) oppure se si desidera trasferire un numero di servizio esistente, consultare [Trasferire i numeri di telefono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> Se sei al di fuori degli Stati Uniti, non puoi utilizzare l'Interfaccia di amministrazione Skype for Business per ottenere i numeri di servizio. Vai su [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization) per sapere cosa fare fuori dagli Stati Uniti.
  
## <a name="step-3---create-a-new-call-queue"></a>Passo 3 - Creare una nuova coda di chiamata

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'Interfaccia di amministrazione di Skype for Business**

Nell' **Interfaccia di amministrazione di Skype for Business**, fai clic su **Instradamento chiamate** > **Code di chiamata**, poi fai clic su **Aggiungi nuova**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Imposta il nome visualizzato della coda di chiamata, il numero di telefono e il dominio (se presente)

![Configurare una coda di chiamata.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Numero 1](../images/sfbcallout1.png)<br/>
**Nome** Immetti un nome descrittivo visualizzato per la coda di chiamata. È obbligatorio e può contenere fino a 64 caratteri, spazi inclusi. <br/> Questo nome verrà visualizzato nella notifica per la chiamata in arrivo.
***
![Numero 2](../images/sfbcallout2.png)<br/>**Numero di telefono** Scegli un numero di servizio (a pagamento o gratuito) per la coda di chiamata. Questo passaggio è facoltativo. <br/> Se non ci sono numeri nell'elenco, devi ottenere numeri di servizio prima di poter creare questa coda di chiamata. Per ottenere i numeri di servizio, consulta [Ottenere numeri di telefono di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md)
***
![Numero 3](../images/sfbcallout3.png)<br/>**Dominio** Se è disponibile, scegli il dominio di Office 365 che desideri utilizzare. Questa opzione è disponibile solo se disponi di più di un dominio utilizzato con Office 365. Se ne hai più di uno, devi scegliere il nome di dominio dall'elenco. <br/> Ad esempio, puoi avere un dominio come:  _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Impostare il saluto e la musica durante l'attesa

![Configurare una coda di chiamata.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>Il **Saluto** è opzionale. Questa è la musica riprodotta per i chiamanti in attesa nella coda di chiamata. <br/> Puoi caricare un file audio (in formato .wav, .mp3 o .wma).
***
![Numero 2](../images/sfbcallout2.png)<br/>**Musica di attesa** Puoi utilizzare la musica di attesa predefinita fornita con la coda di chiamata, oppure caricare un file audio in formato .wav, .wma o .mp3 da utilizzare come musica di attesa personalizzata. 
   

### <a name="select-the-call-distribution-method"></a>Selezionare il metodo di distribuzione di chiamata

![Mostra le opzioni per il metodo di distribuzione delle chiamate](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>**Metodo di distribuzione chiamate** Puoi scegliere **Operatore** o **Seriale** per il metodo di distribuzione della coda di chiamata. Tutte le code di chiamata nuovi ed esistenti hanno l'instradamento operatore selezionato per impostazione predefinita. Per utilizzare l'instradamento seriale, è necessario scegliere l'opzione di instradamento **Seriale** nell'interfaccia utente e nei cmdlet. <br/><br/> Quando si sceglie l'instradamento seriale e viene salvata la coda di chiamata, le chiamate dalla coda squilleranno agli agenti uno alla volta, a partire dall'inizio dell'elenco di agenti. Se un agente rifiuta o non seleziona una chiamata, la chiamata squillerà all'agente successivo nell'elenco e cercherà tutti gli agenti uno alla volta fino a quando non verrà risposta o va in timeout in attesa nella coda.   

> [!NOTE]
> L'instradamento seriale ignorerà gli agenti che sono **Non in linea**, che hanno impostato la presenza su **Non disturbare**o hanno **Rinunciato** scegliendo di non ricevere chiamate da questa coda. 
   
### <a name="select-an-agent-opt-out-option"></a>Selezionare un opzione di esclusione

![Mostra la casella di controllo di esclusione](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>**Opzione esclusione agente** Puoi scegliere di consentire agli agenti di coda di chiamata di disattivare la risposta alle chiamate provenienti da una coda particolare selezionando **Opzione esclusione agente**.  <br/> Attivando questa opzione consentirai a tutti gli agenti nella coda di avviare o interrompere la ricezione di chiamate che proverranno da questa coda di chiamata. Puoi revocare il privilegio di esclusione dell'agente in qualsiasi momento, deselezionando la casella di controllo, includendo nuovamente automaticamente tutti gli agenti a questa coda (impostazione predefinita per tutti gli agenti).  <br/><br/> Per accedere all'opzione di esclusione, gli agenti possono eseguire le seguenti operazioni:
 1. Aprire **Opzioni** nel proprio client desktop di Skype for Business. 
 2. Nella scheda **Inoltro chiamata** di chiamata, fare clic sul collegamento **Modifica impostazioni online**.
 3. Nella pagina Impostazioni utente, fare clic su **Coda chiamate** e quindi deselezionare le caselle di controllo per una o più code per cui desiderano consentire il modo esclusione.
 
    > [!NOTE] 
    > Agenti su Mac, mobile o client Lync 2013 o Hybrid Voice oppure utenti ospitati localmente con Skype per 2015 Business server, possono andare su [https://aka.ms/cqsettings](https://aka.ms/cqsettings) per accedere all'opzione di esclusione.
   
### <a name="add-call-agents-to-a-call-queue"></a>Aggiungere agenti di chiamata a una coda di chiamata

![Configurare code di chiamata.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/><br/>Gli agenti di chiamata (50 massimo) possono essere:
*    Un utente in linea con una licenza di **Sistema telefonico** e abilitato per Enterprise Voice o con un Piano di chiamata. <br/><br/> **Nota:** Per reindirizzare le chiamate agli utenti dell'organizzazione che sono in linea, essi devono disporre di una licenza di **Sistema telefonico** ed essere abilitati per Enterprise Voice o avere Piani di chiamata. Consulta [Assegnare le licenze per i componenti aggiuntivi di Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell. Ad esempio, esegui:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Utenti in linea con una licenza di **Sistema telefonico** e un Piano di chiamata che vengono aggiunti a un Gruppo di Office 365, una lista di distribuzione abilitata alla posta elettronica o un gruppo di protezione. Possono occorrere fino a 30 minuti perché un nuovo agente aggiunto a una lista di distribuzione o gruppo di sicurezza inizi a ricevere chiamate da una coda di chiamata. Un gruppo di protezione o un elenco distribuzione appena creato può richiedere fino a 48 ore per diventare disponibile all'utilizzo con le code di chiamata. I Gruppi di Office 365 appena creati sono disponibili quasi immediatamente. <br/> 

    > [!NOTE] 
    > Gli utenti ospitati localmante con Lync Server 2010 non sono supportati.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Impostare la dimensione massima della coda e il tempo massimo di attesa

![Configurare una coda di chiamata.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/><br/>**Chiamate massime in coda** Consente di impostare il numero massimo di chiamate che possono aspettare in coda contemporaneamente. Il valore predefinito è 50, ma è compreso tra 0 e 200. Quando tale limite viene raggiunto, la chiamata verrà gestita in modo configurato sull'impostazione **Quando viene raggiunto il numero massimo di chiamate** qui sotto.
***
![Numero 2](../images/sfbcallout2.png)<br/><br/>**Quando viene raggiunto il numero massimo di chiamate** Quando la coda di chiamata raggiunge la sua dimensione massima (definita dall'impostazione **Chiamate massime in coda**) puoi scegliere cosa accade alle nuove chiamate in arrivo.
*    **Disconnetti con segnale di occupato** La chiamata verrà disconnessa.
*    **Inoltra a** Quando scegli questa voce avrai le seguenti opzioni:
     *    **Persona nell'azienda** Un utente in linea con una licenza di **Sistema telefonico** e abilitata per Enterprise Voice o un piano di chiamata. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. Per fare ciò, scegli una **Persona nell'azienda** e questa persona riceverà le chiamate inoltrate direttamente sulla segreteria telefonica. <br/> <br/>Per ulteriori informazioni sulle licenze necessarie per la segreteria telefonica, consulta [Configurare i messaggi vocali in Sistema telefonico](/microsoftteams/set-up-phone-system-voicemail). 
     
        > [!Note]
        > Gli utenti ospitati localmante con Lync Server 2010 non sono supportati.<br/>
     
     *    **Coda di chiamata** Devi avere già creato un'altra coda di chiamata, ma dopo averlo fatto puoi selezionare quella coda di chiamata.
     *    **Operatore automatico** Devi avere già creato un operatore automatico, ma dopo averlo fatto puoi selezionare quell'operatore automatico. Consulta [Configurare un operatore automatico di Sistema telefonico](set-up-a-phone-system-auto-attendant.md).
***
![Numero 3](../images/sfbcallout3.png)<br/><br/>**Quanto tempo può aspettare una chiamata in coda** Puoi anche decidere quanto tempo una chiamata può restare in attesa in coda prima che vada in timeout e debba essere reindirizzata o scollegata. La destinazione è basata sull'impostazione **Quando una chiamata va in timeout**. Puoi impostare un tempo da 0 a 45 minuti. <br/><br/> Puoi impostare il valore di timeout in secondi, a intervalli di 15 secondi. In questo modo è possibile modificare il flusso delle chiamate con maggiore granularità. Ad esempio, è possibile specificare che tutte le chiamate che non vengono prese da un agente entro 30 secondi passano a un operatore automatico dell'elenco di ricerca. 

***
![Numero 4](../images/sfbcallout4.png)<br/><br/>**Quando una chiamata va in timeout** Quando la chiamata raggiunge il limite impostato nell'impostazione **Quanto tempo può aspettare una chiamata in coda**, puoi scegliere cosa succede alla chiamata:
*    **Disconnetti** La chiamata verrà disconnessa.
*    **Inoltra a** Quando scegli questa voce avrai le seguenti opzioni:
     *    **Persona nell'azienda** Un utente in linea con una licenza di **Sistema telefonico** e abilitata per Enterprise Voice o Piani di chiamata. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. Per fare ciò, scegli una **Persona nell'azienda** e questa persona riceverà le chiamate inoltrate direttamente sulla segreteria telefonica. </br><br/>  Per ulteriori informazioni sulle licenze necessarie per la segreteria telefonica, consulta [Configurare i messaggi vocali in Sistema telefonico](/microsoftteams/set-up-phone-system-voicemail). 

        > [!Note]
        > Gli utenti ospitati localmante con Lync Server 2010 non sono supportati.<br/>

     *    **Coda di chiamata** Devi avere già creato un'altra coda di chiamata, ma dopo averlo fatto puoi selezionare quella coda di chiamata.
     *    **Operatore automatico** Devi avere già creato un operatore automatico, ma dopo averlo fatto puoi selezionare quell'operatore automatico. Consulta [Configurare un operatore automatico di Sistema telefonico](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modificare l'ID chiamante dell'utente per farlo diventare un numero di telefono della coda di chiamata

Puoi proteggere l'identità di un utente modificando l'ID chiamante per le chiamate in uscita a una coda di chiamata, mediante la creazione di un criterio utilizzando il cmdlet **New-CallingLineIdentity**.
  
Per farlo, esegui quanto segue:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Quindi applica il criterio per l'utente utilizzando il cmdlet ** Grant-CallingLineIdentity.** Per farlo, esegui quanto segue:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

È possibile ottenere ulteriori informazioni su come apportare modifiche alle impostazioni di ID chiamante nell'organizzazione [qui](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Vuoi saperne di più?

Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.
  
### <a name="call-queue-cmdlets"></a>Cmdlet della coda di chiamata

Questi sono i cmdlet necessari per gestire una coda di chiamata.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Altre informazioni su Windows PowerShell

- Windows PowerShell è incentrato sulla gestione degli utenti e su quello che gli utenti sono o non sono autorizzati a fare. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Ecco cosa offre il Sistema telefonico in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
