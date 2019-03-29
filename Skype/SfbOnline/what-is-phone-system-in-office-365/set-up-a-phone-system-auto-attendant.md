---
title: Impostare un operatore automatico del sistema telefonico
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.date: 9/1/2018
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
description: "Informazioni su come configurare e testare gli operatori automatici di sistema telefonico per chiamata efficiente la gestione dell'organizzazione. "
ms.openlocfilehash: ce5b428d678e94d71025eaf8dd659418d05ce8a2
ms.sourcegitcommit: f9a9a7e4b7f6c821a3372f7dcb966a8a6d458752
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2019
ms.locfileid: "30952418"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Impostare un operatore automatico del sistema telefonico

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center. To create a new auto attendant, go to **Call routing** in the left navigation, and then select **Auto attendants** > **Add new**.

Per ulteriori informazioni sugli operatori automatici, vedere [che cosa sono gli operatori automatici di sistema telefonico?](/microsoftteams/what-are-phone-system-auto-attendants)

## <a name="step-1---getting-started"></a>Fase 1 - Attività iniziali

- Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service numbers, they will show up on the **Skype for Business admin center** > **Voice** > **Phone numbers** page. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md), or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365). **User (subscriber)** numbers can't be assigned to auto attendants. If you are outside the United States, you can't use the Skype for Business admin center to get service numbers; go [here](/microsoftteams/manage-phone-numbers-for-your-organization) instead.

    > [!CAUTION]
    > To get and use toll-free phone numbers, you need to set up Communications Credits. To do this see [What are Communications Credits?](/microsoftteams/what-are-communications-credits) and [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for auto attendants. The numbers of auto attendants you can have is dependent on the number **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!TIP]
    > To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). You can also use Windows PowerShell. For example, run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## <a name="step-2---create-a-new-auto-attendant"></a>Fase 2 - Creare un nuovo operatore automatico

 **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams**

**Interfaccia di amministrazione di Microsoft Team**fare clic su ![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **Portale Legacy** >  **routing delle chiamate** > **gli operatori automatici**, quindi fare clic su **Aggiungi nuovo +**:

### <a name="edit-general-info-page"></a>Pagina Modifica informazioni generali

![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>**Name** Enter a descriptive display name for your auto attendant. The name is required and can contain up to 64 characters, including spaces. It will be listed in the **Name** column on the **Auto attendants** tab.
***

![Numero 2](../images/sfbcallout2.png)<br/>**Phone number** This setting is optional. If you like, select a phone number for your auto attendant. You can pick any available service toll or toll-free phone number that you have for your organization. If there are no phone numbers listed, you will need to get a service toll or toll-free phone number. Go [here](getting-service-phone-numbers.md) to get them. <br/> <br/>

> [!NOTE]
> **User (subscriber)** numbers can't be assigned to auto attendants.

***
![Numero 3](../images/sfbcallout3.png)<br/>**Fuso orario** È necessario impostare il fuso orario per l'operatore automatico, che non deve necessariamente corrispondere al fuso orario dell'indirizzo principale indicato per l'organizzazione. Ciascun operatore automatico può avere un fuso orario diverso, e l'orario di ufficio fissato per l'operatore automatico verrà impostato in base al fuso orario che selezioni qui.
***
![14](../images/sfbcallout4.png)<br/>**Language** Select the language that you want to use for your auto attendant from any of the available languages listed. The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.
***
![Numero 5](../images/sfbcallout5.png)<br/>**Speech recognition** Speech recognition is available and if this option is selected. People that call in can use voice input in the language you set. You can disable speech recognition by clearing it if you want to only let people use their phone keypad.
***
![Numero 6](../images/sfbcallout6.png)<br/>**Operator** This is optional and doesn't need to be set for the auto attendant. However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them. <br/> <br/> Il tasto 0 viene assegnato automaticamente alla funzione Operatore. <br/> <br/> If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page. If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option. For example, "For the Operator, press zero." <br/><br/>  Puoi impostare la funzione Operatore a una delle persone seguenti. 
*    **Persona nell'azienda** con una licenza di **Sistema telefonico** abilitata per Enterprise Voice o con Piani di chiamata di Office 365 assegnati. <br/>

     > [!Note] 
     > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 isn't supported. <br/> 

* Una **Coda di chiamata** che hai impostato. 
* You can set it up so the person calling will be sent to voicemail. To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail. 

### <a name="select-hours-of-operation-page"></a>Pagina Seleziona orari di utilizzo

By default, business hours are set to 24 hours a day, 7 days a week, so all hours are considered business hours. All of the hours that aren't included in business hours are considered after business hours. If you select the **Custom** option and set your business hours, then a new page called **After hours call handling** will be added where you can configure the call handling for after business hours for the auto attendant.

![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>Seleziona l'opzione **Personalizzato** per selezionare l'orario di ufficio specifico nel calendario. Quando selezioni **Personalizzato**, l'orario di ufficio sarà impostato da lunedì a venerdì, dalle 9:00 alle 17:00, per impostazione predefinita.
***
![Numero 2](../images/sfbcallout2.png)<br/>To change business hours, highlight the business hours you want to set using the calendar. The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page. To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar. You can set multiple breaks within business hours. 

### <a name="select-business-hours-call-handling-page"></a>Pagina di selezione delle chiamate in orario di ufficio

> [!TIP]
> Se usi un orario di ufficio personalizzato, devi impostare anche la gestione delle chiamate nell'orario di chiusura. Verrà aggiunta una pagina **Gestione delle chiamate in orario di chiusura** per poter configurare queste opzioni, con le stesse opzioni di **Gestione delle chiamate in orario di ufficio**. 

È possibile impostare messaggi di saluto, istruzioni e dei menu di persone che possano rispondere in chiamata al numero di telefono operatore automatico dell'organizzazione durante le ore lavorative.

![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>**Company greeting** Business hours greeting is optional and can be set to **None**. In this case, the caller will hear no message or greeting before the call is handled by one of the options you select. You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.
* **Nessuno** Nessun messaggio di saluto verrà riprodotto quando le persone chiamano il numero di telefono dell'operatore automatico.
*    **Create a custom greeting** If you choose this option, enter the text you want the system to read (up to 1000 characters). For example, you might enter "Welcome to Contoso. Your call is important to us." in the **Callers will hear** box.
* **Caricare un file audio** Se si sceglie questa, registrare il messaggio di saluto e quindi caricare i file audio (in formato WAV, MP3 o. wma).
***
![Numero 2](../images/sfbcallout2.png)<br/>You can select what happens to calls that arrive during business hours. You can chose from the following options:
* **Disconnettere** Se selezionata, la persona che chiama verrà disconnessa dopo aver ascoltato una saluto di orario di ufficio.
* **Reindirizzare una chiamata** Ciò consente di inviare automaticamente la chiamata a:
  * **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. You can set it up so the person calling in can be sent to voicemail. To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/><br/>
    > [!Note]
    > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported. <br/><br/>

  * **Coda di chiamata** Utilizzando una coda di chiamata puoi trasferire la chiamata a una Coda di chiamata esistente che hai configurato.
  * Another **Auto attendant** You can use an existing auto attendant to create a second level of menu options containing a submenu. These are called nested auto attendants.

* **Riprodurre richieste del menu Opzioni** Queste sono anche utilizzabili per consentire la configurazione di una richiesta che si desidera riprodurre.
***
![Numero 3](../images/sfbcallout3.png)<br/>**Messaggio del menu** Per creare il messaggio del menu principale, puoi utilizzare il sintetizzatore vocale o caricare un file audio (.wav, .mp3 o .wma). Puoi digitare il messaggio nella casella **I chiamanti sentiranno** o registrare un file audio e dire, per esempio: "Per assistenza commerciale, premere o pronunciare 1. Per i servizi, premere o pronunciare 2. Per l'assistenza clienti, premere o pronunciare 3. Per contattare un operatore, premere o pronunciare 0. Per ascoltare di nuovo questo menu, premere il tasto asterisco o pronunciare Ripeti". **Crea un messaggio personalizzato** Se scegli questa opzione, devi inserire il testo che vuoi fare leggere al sistema (fino a 1000 caratteri). **Carica un file audio** Se scegli questa opzione, dovrai registrare il messaggio di saluto e poi caricare il file audio (in formato .wav, .mp3 o .wma).
***
![Numero 4](../images/sfbcallout4.png)<br/>**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search. You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page. Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013, can be found with Dial by Name.<br/><br/>  

> [!WARNING]
> Gli utenti ospitati in locale con Lync 2010 **non sono raggiungibili** con Chiamata per nome.
> ***

![Numero 5](../images/sfbcallout5.png)<br/>**Edit menu options** Menu options can be added or removed by using key buttons on the keypad. To add a menu option, press the corresponding key on the keypad. The keys in use will change in color and the corresponding row of options will appear below. To delete a menu option, simply click on the corresponding key on the keypad control to deselect this key. The key mapping row will be removed.<br/><br/>  **Suggerimento:** È necessario aggiornare il testo di richieste di menu o registrare l'audio separatamente, quando si aggiunge alla rimozione di opzioni in quanto non verranno eseguita automaticamente per il prompt dei comandi di menu esistenti.  <br/><br/>  Any menu option can be added and removed in any order, and the key mappings don't have to be continuous. It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.<br/><br/> 

> [!NOTE]
> The keys * (Repeat) and # (Back) are reserved by the system and can't be reassigned. If speech recognition is enabled, pressing * will correspond with "Repeat" and # will correspond with the "Back" voice commands.


Per configurare le opzioni di menu, dopo aver selezionato dei tasti, è necessario: 
- **Enter the Name of the option** This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds." If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3. 
- The next step is to select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition. The call can be sent to: 
    - **Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key. If operator isn't set to any key, then the voice command "Operator" will be disabled too. 
    - A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365. You can set it up so the person calling in can be sent to voicemail. To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.<br/><br/> 

        > [!Note] 
        > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported. <br/><br/>

    - **Coda di chiamata** Utilizzando una coda di chiamata puoi trasferire la chiamata a una Coda di chiamata esistente che hai configurato. 
    - **Auto Attendant** You can use an existing auto attendant to create a second level of menu options containing a submenu. These are called nested auto attendants.<br/><br/>

        > [!Note]
        > Gli **Orari d'ufficio** degli operatori automatici innestati (o di secondo livello) verranno inoltre utilizzate, incluso per le chiamate inviate da altri operatori automatici che sono stati configurati.

### <a name="select-holidays-page"></a>Pagina selezione festività

È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.

![Impostazione di festività per operatore automatico](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>**Aggiungere una festività** Immettere un nome per la nuova festività nel campo **Nome della festività**.<br/><br/> Holiday names may consist of up to 64 characters and must be unique for the same auto attendant. For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.  
***
![Numero 2](../images/sfbcallout2.png)<br/>**Holiday Greeting** The Holiday Greeting is optional and can be set to **None**. In this case, the caller will hear no message or greeting before the call is handled by one of the options you select. You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.
* **Nessuno** Nessun messaggio di saluto verrà riprodotto quando le persone chiamano il numero di telefono dell'operatore automatico.
* **Create a custom greeting** If you choose this option, enter the text you want the system to read (up to 1000 characters). For example, you might enter "Happy New Year! Our offices are currently closed." in the **Callers will hear** box.
* **Caricare un file audio** Se si sceglie questa, registrare il saluto festività e quindi caricare i file audio (in formato WAV, MP3 o. wma).  
***
![Numero 3](../images/sfbcallout3.png)<br/>**What happens to the calls after the greeting?** You can select what happens to the calls that arrive during this holiday. You can chose from the following options:
* **Disconnettere**  La persona chiamata verrà disconnessa dopo aver ascoltato il messaggio di saluto di festività.
* **Reindirizzare una chiamata** Ciò consente di inviare automaticamente la chiamata a:
  * A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. You can set it up so the person calling in can be sent to voicemail. To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail. <br/><br/> 

    > [!Note] 
    > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported.<br/><br/>

  * Una **Coda di chiamata** per trasferire la chiamata a una coda esistente di chiamata che è stata configurata.
  * Another **Auto attendant**, to create a second level of menu options containing a submenu. These are called nested auto attendants. <br/><br/>

    > [!Note]
    > Per impostazione predefinita, per tutte le chiamate in arrivo per un periodo di festività impostate per essere disconnesse dopo il messaggio di saluto (se esistenti), è necessario specificare un reindirizzamento se non si desidera un comportamento diverso.

***
![Numero 4](../images/sfbcallout4.png)<br/>**When do you want the holiday to start and end?** Enter your holiday start date in dd/mm/yyyy format, and then select a start time, end date, and end time, as prompted in the date range table.<br/><br/>You can specify up to 10 different date ranges for a holiday. For example, you could add date ranges for New Year's Eve holidays for up to 10 years. A holiday can span multiple days.<br/><br/>Per aggiungere ulteriori intervalli di date alle festività (ad esempio, per l'anno successivo), fai clic su **Aggiungi un altro**e quindi immetti una nuova serie di date di inizio e fine della festività.<br/><br/>Nested holidays are also supported. For example, you could nest multiple holidays within one "holiday break" time frame: 
* **December 24 through January 3:** "Happy Holidays! Our offices are currently closed. We will reopen on January 4th."
* **December 25:** "Merry Christmas! Our offices are currently closed. We will reopen on January 4th."
* **January 1:** "Happy New Year! Our offices are currently closed. We will reopen on January 4th."

Dopo aver salvato l'operatore automatico, le festività vengono visualizzate nella scheda **Festività**, in cui è possibile editare, aggiungere o modificare le impostazioni di festività.

### <a name="select-dial-scope-page"></a>Pagina Seleziona ambito di chiamata

In questa pagina, è possibile impostare gli utenti nell'organizzazione sarà elencato nella directory e disponibili per l'accesso esterno in base al nome quando una persona che chiama nell'organizzazione.

![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

***
![Numero 1](../images/sfbcallout1.png)<br/>Quando usi l'opzione **Includi** hai a disposizione due opzioni:
* **All Online users** Using this option allows all of the people in your organization to be included in directory search. All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 who have Calling Plans in Office 365, will be listed. 
* **Custom** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. You can add multiple Office 365 Groups, distribution lists, and security groups. <br/><br/> 

  > [!Caution]
  > Gli utenti locali di distribuzioni di Lync Server 2010 non è incluso quando un utente cerca nella directory con accesso esterno in base al nome. 
***
![Numero 2](../images/sfbcallout2.png)<br/>Utilizzo dell'opzione **escludere** , sono disponibili due opzioni:
* **Nessuno** Questa opzione indica che nessun utente online sarà escluso dalla ricerca in elenco. 
* **Custom** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search. You can add multiple Office 365 Groups, distribution lists, and security groups. <br/><br/> 

  > [!Caution]
  > Gli utenti locali di distribuzioni di Lync Server 2010 non è incluso quando un utente cerca nella directory con accesso esterno in base al nome.

> [!NOTE]
> Potrebbe richiedere fino a 36 ore a un nuovo utente a con il nome nell'elenco nella directory quando un utente utilizza Dial per nome da riconoscimento vocale. 

Dopo aver immesso tutti i campi obbligatori e impostare le opzioni di menu e di gestione delle chiamate, fare clic su **Salva**.

## <a name="editing-and-testing-auto-attendants"></a>Modifica e testare gli operatori automatici

After you have saved your auto attendant, it will be listed on the **Auto attendants** page. This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.

Se si desidera apportare modifiche a un operatore automatico, selezionare l'operatore automatico e quindi nel riquadro azioni fare clic su **Modifica**.

È possibile effettuare anche rapidamente una chiamata di prova per l'operatore automatico con il pulsante **Test** nel riquadro azioni.

## <a name="want-to-know-more"></a>Per saperne di più

Puoi anche utilizzare Windows PowerShell per creare e configurare gli operatori automatici.

### <a name="auto-attendant-cmdlets"></a>Cmdlet dell'operatore automatico

Questi sono i cmdlet necessari per gestire un operatore automatico.

|| |
|---  |---  |
| [New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx) | [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx) |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx) | [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx) |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx) | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps) |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx) | [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx) |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx) | [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx) |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx) |
| [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) | [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx) |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx) | [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx) |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx) | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx) | |

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

[Che cosa sono gli operatori automatici del sistema telefonico?](/MicrosoftTeams/what-are-phone-system-auto-attendants.md)

[Esempio per piccole imprese - Impostare un operatore automatico](tutorial-org-aa.yml)  
