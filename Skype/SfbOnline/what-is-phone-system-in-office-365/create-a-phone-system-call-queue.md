---
title: Creare una coda di chiamate del sistema telefonico
author: Jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: phans, wasseemh
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
f1keywords: ms.teamsadmincenter.callqueues.overview
ms.custom:
- Phone System
description: "Informazioni su come configurare Sistema telefonico per le code di chiamata di Office 365 (Cloud PBX) per fornire un messaggio di saluto, una musica di attesa e per reindirizzare le chiamate ad agenti nelle liste di distribuzione e gruppi di protezione dell'organizzazione. È inoltre possibile impostare la dimensione massima della coda, il timeout e le opzioni di gestione delle chiamate. "
ms.openlocfilehash: c76f7e00c8c12e79c0dc333e05d4ccb0ca75266a
ms.sourcegitcommit: f9a9a7e4b7f6c821a3372f7dcb966a8a6d458752
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2019
ms.locfileid: "30952352"
---
# <a name="create-a-phone-system-call-queue"></a>Creare una coda di chiamate del sistema telefonico

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.
  
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
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per ulteriori informazioni sui piani di chiamata di Office 365, vedere [sistema telefonico e la chiamata a piani](/microsoftteams/calling-plan-landing-page) e [La chiamata a piani per Office 365](/microsoftteams/calling-plans-for-office-365).

    > [!NOTE]
    > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati come un agenti di coda di chiamata. 
  
- You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.

    > [!NOTE]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati a code di chiamata, ma solo numeri di telefono di servizio a pagamento o numeri verdi. 
  
- Quando si distribuiscono le chiamate in arrivo dalla coda di chiamata di un sistema telefonico, questi client sono supportati per gli agenti di chiamata:

  - Client desktop Skype for Business 2016 (versioni a 32 e 64 bit)

  - Client desktop Lync 2013 (versioni a 32 e 64 bit)

  - All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).

  - Client Mac Skype for Business (versione 16.8.196 e versioni successive) 

  - Client Android Skype for Business (versione 6.16.0.9 e versioni successive)

  - Client iPhone Skype for Business (versione 6.16.0 e versioni successive)

  - Client Mac Skype for Business (versione 6.16.0 e versioni successive)

  - Client Microsoft Teams Windows (versioni a 32 e 64 bit)

  - Client Microsoft Teams Mac

  - Microsoft Teams iPhone app

  - Team di Microsoft app Android

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Fase 2 - Ottenere o trasferire numeri di servizio a pagamento o a numero verde

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.
  
## <a name="step-3---create-a-new-call-queue"></a>Fase 3 - Creare una nuova coda di chiamata

 **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams**

**Interfaccia di amministrazione di Microsoft Team**fare clic su ![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **Portale Legacy** >  **routing delle chiamate** > **code di chiamata**, quindi fare clic su **Aggiungi nuovo +**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Imposta il nome visualizzato della coda di chiamata, il numero di telefono e il dominio (se presente)

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Numero 1](../images/sfbcallout1.png)<br/>
**Nome** Immetti un nome visualizzato descrittivo per la coda di chiamata. È obbligatorio e può contenere fino a 64 caratteri, spazi inclusi.<br/> Questo nome verrà visualizzato nella notifica per la chiamata in arrivo.
***
![Numero 2](../images/sfbcallout2.png)<br/>**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. <br/> If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)
***
![Numero 3](../images/sfbcallout3.png)<br/>**Dominio** Se è disponibile, scegli il dominio di Office 365 che desideri utilizzare. Questa opzione è disponibile solo se disponi di più di un dominio utilizzato con Office 365. Se ne hai più di uno, devi scegliere il nome di dominio dall'elenco. <br/> Ad esempio, puoi avere un dominio come:  _contoso.com or redmond.contoso.com_

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Impostare il saluto e la musica durante l'attesa

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. <br/> È possibile caricare un file audio (formati. wav, MP3 o. wma).
***
![Numero 2](../images/sfbcallout2.png)<br/>**Musica di attesa** È possibile utilizzare l'impostazione predefinita, la musica di attesa fornita con la coda chiamata oppure è possibile caricare un file audio nel formato con estensione wav, mp3 o. wma da utilizzare come musica personalizzata in attesa.

### <a name="select-the-call-distribution-method"></a>Selezionare il metodo di distribuzione di chiamata

![Mostra le opzioni per il metodo di distribuzione delle chiamate](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. <br/><br/> When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.   

> [!NOTE]
> L'instradamento seriale ignorerà gli agenti che sono **Non in linea**, che hanno impostato la presenza su **Non disturbare**o hanno **Rinunciato** scegliendo di non ricevere chiamate da questa coda. 

### <a name="select-an-agent-opt-out-option"></a>Selezionare un opzione di esclusione

![Mostra la casella di controllo di esclusione](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/>**Opzione esclusione agente** Puoi scegliere di consentire agli agenti di coda di chiamata di disattivare la risposta alle chiamate provenienti da una coda particolare selezionando **Opzione esclusione agente**.  <br/> Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  <br/><br/> Per accedere all'opzione di esclusione, gli agenti possono eseguire le seguenti operazioni:
 1. Aprire **Opzioni** nel proprio client desktop di Skype for Business. 
 2. Nella scheda **Inoltro chiamata** di chiamata, fare clic sul collegamento **Modifica impostazioni online**.
 3. Nella pagina Impostazioni utente, fare clic su **Coda chiamate** e quindi deselezionare le caselle di controllo per una o più code per cui desiderano consentire il modo esclusione.

    > [!NOTE] 
    > Agenti su Mac, mobile o client Lync 2013 o Hybrid Voice oppure utenti ospitati localmente con Skype per 2015 Business server, possono andare su [https://aka.ms/cqsettings](https://aka.ms/cqsettings) per accedere all'opzione di esclusione.

### <a name="add-call-agents-to-a-call-queue"></a>Aggiungere agenti di chiamata a una coda di chiamata

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/><br/>Gli agenti di chiamata (massimo 200) possono essere:
* Un utente in linea con una licenza di **Sistema telefonico** e abilitato per Enterprise Voice o con un Piano di chiamata. <br/><br/> **Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. <br/> 

  > [!NOTE] 
  > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.

### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Impostare la dimensione massima della coda e il tempo massimo di attesa

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/><br/>**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.
***
![Numero 2](../images/sfbcallout2.png)<br/><br/>**Quando viene raggiunto il numero massimo di chiamate** Quando la coda di chiamate raggiunge la dimensione massima (impostata utilizzando l'impostazione **massimo chiama nella coda** ), è possibile scegliere cosa accade a nuove chiamate in arrivo.
* **Disconnetti con segnale di occupato** La chiamata verrà disconnessa.
* **Inoltrare la chiamata** Quando si sceglie questo, si disporrà di queste opzioni:
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/> <br/>Per ulteriori informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurazione di segreteria telefonica Cloud](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.<br/>

  * **Coda di chiamata** È necessario avere già creato un'altra coda di chiamata, ma dopo aver eseguito, è possibile selezionare la coda di chiamata.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
***
![Numero 3](../images/sfbcallout3.png)<br/><br/>**Quanto tempo può aspettare una chiamata in coda** Puoi anche decidere quanto tempo una chiamata può restare in attesa in coda prima che vada in timeout e debba essere reindirizzata o scollegata. La destinazione è basata sull'impostazione **Quando una chiamata va in timeout**. Puoi impostare un tempo da 0 a 45 minuti. <br/><br/> The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant. 

***
![Numero 4](../images/sfbcallout4.png)<br/><br/>**Quando una chiamata va in timeout** Quando la chiamata raggiunge il limite impostato nell'impostazione **Quanto tempo può aspettare una chiamata in coda**, puoi scegliere cosa succede alla chiamata:
* **Disconnetti** La chiamata verrà disconnessa.
* **Inoltrare la chiamata** Quando si sceglie questo, si disporrà di queste opzioni:
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </br><br/>  Per ulteriori informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurazione di segreteria telefonica Cloud](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.<br/>

  * **Coda di chiamata** È necessario avere già creato un'altra coda di chiamata, ma dopo aver eseguito, è possibile selezionare la coda di chiamata.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modificare l'ID chiamante dell'utente per farlo diventare un numero di telefono della coda di chiamata

Puoi proteggere l'identità di un utente modificando l'ID chiamante per le chiamate in uscita a una coda di chiamata, mediante la creazione di un criterio utilizzando il cmdlet **New-CallingLineIdentity**.
  
Per farlo, eseguire quanto segue:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:
  
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

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:

  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:

  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Argomenti correlati
[Ecco cosa offre il Sistema telefonico in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
