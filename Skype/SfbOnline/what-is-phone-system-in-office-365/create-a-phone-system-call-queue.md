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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 742fdbf38aeb64426ad1781d552c580385dc8117
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531835"
---
# <a name="create-a-phone-system-call-queue"></a>Creare una coda di chiamata del Sistema telefonico

Chiamata al sistema telefonico code includono messaggi di saluto che vengono utilizzati quando si riceve una chiamata a un numero di telefono per l'organizzazione, la possibilità di inserire automaticamente le chiamate in attesa e le funzionalità di ricerca per il successivo agente disponibile chiamata gestire la chiamata mentre gli utenti che chiamata in attesa la musica di attesa. È possibile creare uno o più code di chiamata per l'organizzazione.
  
Le code di chiamata di Sistema possono fornire:
  
- Un saluto aziendale.
- Musica mentre le persone sono in attesa.
- Reindirizzamento delle chiamate per chiamare agenti in gruppi di protezione e le liste di distribuzione abilitati alla posta elettronica.
- Configurare le impostazioni per la dimensione massima della coda di chiamata, timeout e le opzioni di gestione delle chiamate.

Quando si riceve una chiamata a un numero di telefono che è configurato con una coda di chiamata, verranno sentire un messaggio di saluto principale (se una configurazione), quindi verrà inserito in coda e attendere il successivo agente disponibile chiamata. Il chiamante ascolterà la musica durante l'attesa, e le chiamate verranno inoltrate agli agenti di chiamata in ordine  *FIFO (First In, First Out - Primo arrivato, primo servito)*  .
  
Tutte le chiamate in attesa nella coda verranno distribuite tramite una modalità routing operatore oppure la modalità di routing seriale:
  
- Con l'operatore di routing, la prima chiamata nella coda deve squillare tutti gli agenti contemporaneamente.
- Con l'instradamento seriale, la prima chiamata della squillerà a tutti gli agenti di chiamata uno alla volta.

    > [!NOTE]
    > Non verranno chiamati agli agenti chiamata che sono **Non in linea**, che hanno impostato la presenza su **Non disturbare,** oppure sono usciti dalla coda di chiamata.
  
- Solo una notifica di chiamata in arrivo (per la chiamata in cima alla coda) per volta viene inviata agli agenti di chiamata.
- Una volta che un agente di chiamata accetta la chiamata, la prossima chiamata in arrivo in coda viene segnalata agli agenti di chiamata.

## <a name="step-1---getting-started"></a>Fase 1 - Attività iniziali

Per iniziare a utilizzare le code di chiamata, è importante ricordare quanto segue.
  
- L'organizzazione deve disporre (almeno) una licenza Enterprise E3 plus **Sistema telefonico** o una licenza Enterprise E5. Il numero di licenze utente **Sistema telefonico** assegnati influisce sul numero dei numeri di servizio disponibili essere utilizzati per le code di chiamata. Il numero di code di chiamata che è possibile avere dipende il numero di licenze **Sistema telefonico** e **Audioconferenza** assegnati all'interno dell'organizzazione. Per ulteriori informazioni sulle licenze, Vai [qui](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Per reindirizzare le chiamate agli utenti dell'organizzazione che sono in linea, che deve disporre di una licenza di **Sistema telefonico** e abilitati per Enterprise Voice o dispone prevede la chiamata di Office 365. Vedere [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell. Ad esempio, eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per ulteriori informazioni sui piani di chiamata di Office 365, consulta [Che cosa sono i Piani di chiamata in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)  e [Piani di chiamata per Office 365](/microsoftteams/calling-plans-for-office-365).

    > [!NOTE]
    > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati come un agenti di coda di chiamata. 
  
- È possibile assegnare solo numeri telefonici di servizio a pagamento e gratuiti anche nell'**Interfaccia di amministrazione di Skype fpr Business** o trasferire da un altro provider di servizi a code di chiamata di Sistema telefonico. Per ottenere e utilizzare i numeri gratuiti, è necessario impostare il Credito per la comunicazione.

    > [!NOTE]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati a code di chiamata, ma solo numeri di telefono di servizio a pagamento o numeri verdi. 
  
- Quando si distribuiscono le chiamate in arrivo dalla coda di chiamata di un sistema telefonico, questi client sono supportati per gli agenti di chiamata:

  - Client desktop Skype for Business 2016 (versioni a 32 e 64 bit)

  - Client desktop Lync 2013 (versioni a 32 e 64 bit)

  - Tutti i modelli di telefoni IP supportati per Skype for Business online. Vedere [Getting telefoni Skype Business online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).

  - Client Mac Skype for Business (versione 16.8.196 e versioni successive) 

  - Client Android Skype for Business (versione 6.16.0.9 e versioni successive)

  - Client iPhone Skype for Business (versione 6.16.0 e versioni successive)

  - Client Mac Skype for Business (versione 6.16.0 e versioni successive)

  - Client Microsoft Teams Windows (versioni a 32 e 64 bit)

  - Client Microsoft Teams Mac

  - Microsoft Teams iPhone app

  - Team di Microsoft app Android

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Fase 2 - Ottenere o trasferire numeri di servizio a pagamento o a numero verde

Prima di poter creare e configurare le code di chiamata, è necessario ottenere numeri di servizio a pagamento o meno oppure  trasferire quelli esistenti. Dopo aver ottenuto i numeri di servizio, a pagamento o meno, questi verranno visualizzati nell'interfaccia di amministrazione di **Skype per Business** > **Vocale** > **Numeri di telefono** e **Tipo di numero** elencato verrà indicato come **Servizio - numero verde**. Per ottenere i numeri di servizio, vedere [Ottenere numeri di telefono di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md) oppure se si desidera trasferire un numero di servizio esistente, consultare [Trasferire i numeri di telefono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> Se si è fuori degli Stati Uniti, è possibile utilizzare Skype per interfaccia di amministrazione di Business per ottenere i numeri di servizio. Vai a [Gestisci i numeri di telefono per l'organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization) ma per informazioni su come effettuare di fuori degli Stati Uniti.
  
## <a name="step-3---create-a-new-call-queue"></a>Fase 3 - Creare una nuova coda di chiamata

 **Utilizzo del team di Microsoft Skype per Business Admin Center**

Il **team di Microsoft e Skype per Business Admin Center**, fare clic su ![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **Portale Legacy** >  **routing delle chiamate** > **code di chiamata**, quindi fare clic su **Aggiungi nuovo +**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Imposta il nome visualizzato della coda di chiamata, il numero di telefono e il dominio (se presente)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Numero 1](../images/sfbcallout1.png)<br/>
**Nome** Immetti un nome visualizzato descrittivo per la coda di chiamata. È obbligatorio e può contenere fino a 64 caratteri, spazi inclusi.<br/> Questo nome verrà visualizzato nella notifica per la chiamata in arrivo.
***
![Numero 2](../images/sfbcallout2.png)<br/>**Numero di telefono** Scegli un numero di servizio (a pagamento o numero verde) per la coda di chiamata. Ciò è facoltativa. <br/> Se non ci sono numeri in elenco, devi ottenere numeri di servizio prima di poter creare questa coda di chiamata. Per ottenere i numeri di servizio, vedere [Getting numeri di telefono del servizio per Skype per le aziende e team di Microsoft](getting-service-phone-numbers.md)
***
![Numero 3](../images/sfbcallout3.png)<br/>**Dominio** Se è disponibile, scegli il dominio di Office 365 che desideri utilizzare. Questa opzione è disponibile solo se disponi di più di un dominio utilizzato con Office 365. Se ne hai più di uno, devi scegliere il nome di dominio dall'elenco. <br/> Ad esempio, puoi avere un dominio come:  _contoso.com or redmond.contoso.com_

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Impostare il saluto e la musica durante l'attesa

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>Il **Saluto** è opzionale. Questo è il messaggio di saluto riprodotto per gli utenti che chiamano per il numero di coda di chiamata. <br/> È possibile caricare un file audio (formati. wav, MP3 o. wma).
***
![Numero 2](../images/sfbcallout2.png)<br/>**Musica di attesa** È possibile utilizzare l'impostazione predefinita, la musica di attesa fornita con la coda chiamata oppure è possibile caricare un file audio nel formato con estensione wav, mp3 o. wma da utilizzare come musica personalizzata in attesa.

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

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/><br/>Gli agenti di chiamata (50 massimo) possono essere:
* Un utente in linea con una licenza di **Sistema telefonico** e abilitato per Enterprise Voice o con un Piano di chiamata. <br/><br/> **Nota:**  Per reindirizzare le chiamate agli utenti dell'organizzazione che sono in linea, che deve disporre di una licenza di **Sistema telefonico** e abilitati per Enterprise Voice o disporre di un piano di chiamata. Vedere [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell. Ad esempio, eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* Utenti in linea con una licenza di **Sistema telefonico** e un Piano di chiamata che vengono aggiunti a un Gruppo di Office 365, una lista di distribuzione abilitata alla posta elettronica o un gruppo di protezione. Possono occorrere fino a 30 minuti perché un nuovo agente aggiunto a una lista di distribuzione o gruppo di sicurezza inizi a ricevere chiamate da una coda di chiamata. Un gruppo di sicurezza o elenco distribuzione appena creata può richiedere fino a 48 ore per diventare disponibili per l'utilizzo con le code di chiamata. I Gruppi di Office 365 appena creati sono disponibili quasi immediatamente. <br/> 

  > [!NOTE] 
  > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.

### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Impostare la dimensione massima della coda e il tempo massimo di attesa

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/><br/>**Chiamate massime in coda** Consente di impostare il numero massimo di chiamate che possono aspettare in coda contemporaneamente. Il valore predefinito è 50, ma compreso tra 0 e 200. quando tale limite viene raggiunto, la chiamata verrà gestita in modo impostate sull'impostazione **quando viene raggiunto il numero massimo di chiamate** .
***
![Numero 2](../images/sfbcallout2.png)<br/><br/>**Quando viene raggiunto il numero massimo di chiamate** Quando la coda di chiamate raggiunge la dimensione massima (impostata utilizzando l'impostazione **massimo chiama nella coda** ), è possibile scegliere cosa accade a nuove chiamate in arrivo.
* **Disconnetti con segnale di occupato** La chiamata verrà disconnessa.
* **Inoltrare la chiamata** Quando si sceglie questo, si disporrà di queste opzioni:
  * **Persona nell'azienda** Un utente in linea con una licenza di **Sistema telefonico** e abilitato per Enterprise Voice o un piano di chiamata. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. A tale scopo, selezionare una **persona nell'azienda** e impostare tale persona per le chiamate inoltrate direttamente alla segreteria telefonica. <br/> <br/>Per ulteriori informazioni sulle licenze necessarie per la segreteria telefonica, consulta [Configurare i messaggi vocali in Sistema telefonico](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.<br/>

  * **Coda di chiamata** È necessario avere già creato un'altra coda di chiamata, ma dopo aver eseguito, è possibile selezionare la coda di chiamata.
  * **Operatore automatico** È necessario avere già creato un operatore automatico, ma dopo aver eseguito, è possibile selezionare tale operatore automatico. Vedere [configurare un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).
***
![Numero 3](../images/sfbcallout3.png)<br/><br/>**Quanto tempo può aspettare una chiamata in coda** Puoi anche decidere quanto tempo una chiamata può restare in attesa in coda prima che vada in timeout e debba essere reindirizzata o scollegata. La destinazione è basata sull'impostazione **Quando una chiamata va in timeout**. Puoi impostare un tempo da 0 a 45 minuti. <br/><br/> Puoi impostare il valore di timeout in secondi, a intervalli di 15 secondi. In questo modo è possibile modificare il flusso delle chiamate con maggiore granularità. Ad esempio, è possibile specificare che tutte le chiamate che non vengono prese da un agente entro 30 secondi passano a un operatore automatico dell'elenco di ricerca. 

***
![Numero 4](../images/sfbcallout4.png)<br/><br/>**Quando una chiamata va in timeout** Quando la chiamata raggiunge il limite impostato nell'impostazione **Quanto tempo può aspettare una chiamata in coda**, puoi scegliere cosa succede alla chiamata:
* **Disconnetti** La chiamata verrà disconnessa.
* **Inoltrare la chiamata** Quando si sceglie questo, si disporrà di queste opzioni:
  * **Persona nell'azienda** Un utente in linea con una licenza di **Sistema telefonico** e abilitato per Enterprise Voice o piani di chiamata. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. A tale scopo, selezionare una **persona nell'azienda** e impostare tale persona per le chiamate inoltrate direttamente alla segreteria telefonica. </br><br/>  Per ulteriori informazioni sulle licenze necessarie per la segreteria telefonica, consulta [Configurare i messaggi vocali in Sistema telefonico](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.<br/>

  * **Coda di chiamata** È necessario avere già creato un'altra coda di chiamata, ma dopo aver eseguito, è possibile selezionare la coda di chiamata.
  * **Operatore automatico** È necessario avere già creato un operatore automatico, ma dopo aver eseguito, è possibile selezionare tale operatore automatico. Vedere [configurare un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modificare l'ID chiamante dell'utente per farlo diventare un numero di telefono della coda di chiamata

Puoi proteggere l'identità di un utente modificando l'ID chiamante per le chiamate in uscita a una coda di chiamata, mediante la creazione di un criterio utilizzando il cmdlet **New-CallingLineIdentity**.
  
Per farlo, eseguire quanto segue:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Quindi applica il criterio per l'utente utilizzando il cmdlet ** Grant-CallingLineIdentity.** Per farlo, eseguire quanto segue:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

È possibile ottenere ulteriori informazioni su come apportare modifiche alle impostazioni di ID chiamante nell'organizzazione [qui](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Per saperne di più

Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.
  
### <a name="call-queue-cmdlets"></a>Cmdlet della coda di chiamata

Questi sono i cmdlet necessari per gestire una coda di chiamata.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)

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
[Ecco cosa offre il Sistema telefonico in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
