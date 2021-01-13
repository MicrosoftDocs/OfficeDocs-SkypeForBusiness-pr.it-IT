---
title: Processo di distribuzione per Response Group in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Processo di distribuzione e passaggi per Response Group in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: cec795b5215caa81b281379cd4c433563ccebf83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812326"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Processo di distribuzione per Response Group in Skype for business

Processo di distribuzione e passaggi per Response Group in Skype for Business Server VoIP aziendale.

Response Group è una funzionalità di VoIP aziendale che consente di instradare e accodare le chiamate in arrivo a gruppi di utenti, denominati agenti, ad esempio un helpdesk o un desk del servizio clienti.

I componenti necessari per Response Group vengono installati e abilitati automaticamente nel server Standard Edition o Front End Server quando si distribuisce VoIP aziendale. Per rendere Response Group disponibile agli utenti, è necessario configurare i gruppi di agenti, quindi le code e quindi i flussi di lavoro. Inoltre, un amministratore di Response Group può delegare la configurazione di un flusso di lavoro esistente a un responsabile del gruppo di risposta, che può quindi modificare e riconfigurare il flusso di lavoro e i gruppi di agenti e le code associati.

Per configurare i Response Group, è necessario essere membri di almeno uno dei ruoli amministrativi seguenti:

|**Gruppo di sicurezza Active Directory (1)** <br/> |Creare flusso di lavoro  <br/> |Assegnare responsabile  <br/> |Creare/assegnare agenti, code  <br/> |Creare/gestire festività e orari di ufficio  <br/> |Attivare/disattivare il flusso di lavoro  <br/> |Configurare il flusso di lavoro (IVR o gruppo di risposta)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√ (2)  <br/> |√ (3)  <br/> |√ (3)  <br/> |√ (3)  <br/> |√ (3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |

> [!NOTE]
> **(1)** un oggetto utente di servizi di dominio Active Directory deve essere membro del gruppo di sicurezza di Active Directory specificato elencato. Un amministratore o un altro membro del gruppo di Active Directory delegato con le autorizzazioni appropriate per aggiungere gli utenti a un gruppo di sicurezza (ad esempio, Administrator, account Operators) deve aggiungere un oggetto utente al gruppo o al gruppo di sicurezza elencato per consentire all'utente di eseguire le funzioni elencate. **(2)** solo per i flussi di lavoro assegnati da CsResponseGroupAdministrator a CsResponseGroupManager. **(3)** un responsabile di Response Group può assegnare un altro membro di CsResponseGroupManager a un flusso di lavoro che il Manager corrente gestisce già. **(4)** CsViewOnlyAdministrator è in grado di eseguire solo i cmdlet "Get" dei verbi.

## <a name="response-group-configuration-prerequisites"></a>Prerequisiti di configurazione di Response Group

Per Response Group sono necessari i componenti seguenti:

- Servizio applicazione

- Applicazione Response Group

- Language Pack

- Archivio file (per gestire i file audio)

- Servizi Web (include lo strumento di configurazione di Response Group e la console di accesso e disconnessione degli agenti)

Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.

Prima di configurare Response Group potrebbe essere necessario eseguire le attività seguenti:

- Abilitare gli utenti per Lync Server 2013 e VoIP aziendale.

- Modificare un file di configurazione in modo che sia conforme agli standard FIPS (Federal Information Processing Standard).

- Modificare le regole di confronto del database per supportare caratteri Yi, Meng e Zang per i nomi di code e i nomi dei gruppi di agenti.

### <a name="enabling-users"></a>Abilitazione degli utenti

Il primo passaggio per la configurazione di Response Group consiste nella creazione di gruppi di agenti. Prima di poter creare un gruppo di agenti, è necessario abilitare gli utenti che saranno agenti di Response Group per Skype for business e VoIP aziendale. L'abilitazione degli utenti per Skype for business è in genere un passaggio del server Enterprise Edition o della distribuzione del server Standard Edition. Per informazioni dettagliate sull'abilitazione degli utenti per Skype for business, vedere [Enable or Disable users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). L'abilitazione degli utenti per VoIP aziendale è in genere un passaggio della distribuzione di VoIP aziendale. Per ulteriori informazioni, vedere [abilitare gli utenti per VoIP aziendale in Skype for Business Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Conformità ai requisiti FIPS

Fare riferimento a questa sezione solo se l'organizzazione deve essere conforme agli standard FIPS (Federal Information Processing Standards).

Per essere conformi a FIPS, è necessario modificare il file Web.config a livello dell'applicazione in modo da usare un algoritmo di crittografia diverso dopo aver installato Servizi Web. È necessario specificare l'uso dell'algoritmo 3DES (Triple Data Encryption Standard) per ASP.NET per l'elaborazione dei dati sugli stati di visualizzazione. Per l'applicazione Response Group, questo requisito si applica allo strumento di configurazione di Response Group e alla console di accesso e disconnessione dell'agente. Per informazioni dettagliate su questo requisito, vedere l'articolo 911722 della Microsoft Knowledge Base "è possibile che venga visualizzato un messaggio di errore quando si accede alle pagine Web di ASP.NET che dispongono di ViewState abilitato dopo l'aggiornamento da ASP.NET 1,1 a ASP.NET 2,0" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183) .

Per modificare il file Web.config, eseguire le operazioni seguenti:

1. In un editor di testo come Blocco note aprire il file Web.config a livello dell'applicazione.

2. Nel file Web.config individuare la  `<system.web>` sezione.

3. Aggiungere la  `<machineKey>` sezione seguente alla `<system.web>` sezione:

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Salvare il file Web.config.

5. Riavviare il servizio Internet Information Services (IIS) eseguendo il comando seguente al prompt dei comandi:

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Supporto di caratteri Yi, Meng e Zang

Fare riferimento a questa sezione solo se l'organizzazione richiede il supporto di caratteri Yi, Meng o Zang.

> [!NOTE]
> Per informazioni su ciò che sono i caratteri Yi, Meng e Zang e il motivo per cui possono essere importanti per la distribuzione, vedere le informazioni sui set di caratteri di GB18030 [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223) .

Per il supporto di caratteri Yi, Meng o Zang è necessario modificare le regole di confronto del database Rgsconfig. Modificare le regole di confronto della colonna **Name** nelle tabelle seguenti di ogni database Rgsconfig:

- dbo. AgentGroups

- dbo. BusinessHours

- dbo. HolidaySets

- dbo. Code

- dbo. Flussi

Per SQL Server 2008 R2 e SQL Server 2012, utilizzare le regole di confronto Latin_General_100 (sensibile all'accento). Se si utilizzano queste regole di confronto, la distinzione tra maiuscole e minuscole non viene applicata ad alcun nome di oggetto.

È possibile modificare le regole di confronto utilizzando Microsoft SQL Server Management Studio. Per informazioni dettagliate sull'utilizzo di questo strumento, vedere ["using SQL Server Management Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184). Per modificare le regole di confronto, eseguire la procedura seguente:

1. Verificare che SQL Server Management Studio sia configurato per consentire modifiche che richiedono la ricreazione di tabelle. Per informazioni dettagliate, vedere la finestra di [dialogo Salva (non consentita)](https://go.microsoft.com/fwlink/p/?linkId=196186). Per informazioni dettagliate sull'impostazione di una regola di confronto delle colonne, vedere ["procedura: impostare le regole di confronto delle colonne (Visual Database Tools)"](https://go.microsoft.com/fwlink/p/?linkId=196185).

2. Utilizzando Microsoft SQL Server Management Studio connettersi al database Rgsconfig.

3. Trovare la tabella che si desidera modificare nel database Rgsconfig, fare clic con il pulsante destro del mouse sulla tabella e quindi scegliere **Progetta**.

4. Modificare le regole di confronto della colonna **Name** e salvare la tabella.

## <a name="response-group-deployment-steps"></a>Passaggi per la distribuzione di Response Group

**Processo di distribuzione di Response Group**

|**Fase**|**Procedura**|**Autorizzazioni**|**Documentazione relativa alla distribuzione**|
|:-----|:-----|:-----|:-----|
|Abilitare gli utenti per Skype for business e per VoIP aziendale  <br/> |Abilitare gli utenti che saranno agenti per Skype for business e VoIP aziendale. Gli utenti devono essere abilitati per poter essere aggiunti a gruppi di agenti. In genere, gli utenti sono abilitati per Skype for business durante la distribuzione di Enterprise Edition o del server Standard Edition. Gli utenti sono abilitati per VoIP aziendale durante la distribuzione di VoIP aziendale.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Abilitare o disabilitare gli utenti per l'anteprima di Lync Server 2013](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Abilitare gli utenti per VoIP aziendale in Skype for Business Server](enable-users-for-enterprise-voice.md) <br/> |
|Creazione e configurazione di Response Group, costituiti da gruppi di agenti, code e flussi di lavoro  <br/> |1. usare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per eseguire le operazioni seguenti:  <br/> a. Creare e configurare gruppi di agenti.  <br/> b. Creare e configurare code.  <br/> 2. Facoltativamente, utilizzare Skype for Business Server Management Shell per creare le festività e gli orari di ufficio di Response Group predefiniti.  <br/> 3. utilizzare lo strumento di configurazione di Response Group o Skype for Business Server Management Shell per creare flussi di lavoro (gruppi di risposta o flussi di chiamate IVR), compresi gli orari di ufficio e le festività di Response Group personalizzati.  <br/> È possibile accedere allo strumento di configurazione di Response Group tramite il pannello di controllo di Skype for Business Server.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Creare gruppi di agenti per Response Group](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Creare code di Response Group](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [Optional Definire l'orario di ufficio di Response Group in Skype for business](optional-define-response-group-business-hours.md) <br/> [Optional Definire i set di festività di Response Group in Skype for business](optional-define-response-group-holiday-sets.md) <br/> [Progettazione e creazione di flussi di lavoro di Response Group in Skype for business](designing-and-creating-response-group-workflows.md) <br/> |
|(Facoltativo) Personalizzazione delle impostazioni a livello di applicazione  <br/> |Utilizzare Skype for Business Server Management Shell per personalizzare la configurazione predefinita per la musica in attesa, il file audio predefinito per la musica in attesa, il periodo di richiamata dell'agente e la configurazione del contesto delle chiamate.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Gestione delle impostazioni di Response Group a livello di applicazione in Skype for business](managing-application-level-response-group-settings.md) <br/> |
|(Facoltativo) Delega della gestione dei Response Group  <br/> |Assegnare agli utenti il ruolo CsResponseGroupManager per delegare la configurazione dei Response Group. I responsabili dei Response Group possono quindi configurare i Response Group a loro assegnati.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Pianificazione del controllo di accesso basato sui ruoli](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Verificare la distribuzione di Response Group  <br/> |Testare la risposta alle chiamate nei flussi di lavoro del gruppo di risposta e del sistema IVR per assicurare che la configurazione funzioni come previsto.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Panoramica degli scenari di creazione del flusso di lavoro

Quando si creano flussi di lavoro, i possibili scenari sono due:

- **L'amministratore crea e configura il flusso di lavoro** - Il membro del ruolo CsResponseGroupAdministrator (o equivalente) crea e attiva il flusso di lavoro e tutti i relativi elementi, ad esempio gruppi di agenti, code, festività, orario di ufficio, musica di attesa e così via.

- **L'amministratore crea il flusso di lavoro e il manager configura le opzioni** - Il membro del ruolo CsResponseGroupAdministrator (o equivalente) definisce l'URI SIP primario, assegna uno o più membri al ruolo CsResponseGroupManager, quindi seleziona una coda e attiva il flusso di lavoro. Il membro del ruolo CsResponseGroupManager può quindi effettuare l'accesso e modificare la configurazione del flusso di lavoro creando gruppi di agenti. Assegna inoltre il gruppo alla coda, configurando il numero di telefono, festività, orario di ufficio, musica di attesa e così via.

    > [!NOTE]
    > Se si vuole creare un flusso di lavoro gestito è necessario crearlo come attivo. Dopo aver salvato un flusso di lavoro gestito e attivo, sarà possibile modificarlo e disattivarlo.


