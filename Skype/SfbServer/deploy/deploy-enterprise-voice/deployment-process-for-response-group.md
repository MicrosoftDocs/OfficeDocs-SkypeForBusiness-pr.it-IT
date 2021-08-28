---
title: Processo di distribuzione per Response Group in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Processo di distribuzione e passaggi per Response Group in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 1cb85ac95025b71de8a071758befb5287a6fafa4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620182"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Processo di distribuzione per Response Group in Skype for Business

Processo di distribuzione e passaggi per Response Group in Skype for Business Server VoIP aziendale.

Response Group è una funzionalità VoIP aziendale che instrada e accoda le chiamate in arrivo a gruppi di persone, denominati agenti, ad esempio un help desk o un servizio clienti.

I componenti necessari per Response Group vengono installati e abilitati automaticamente nel server Standard Edition o Front End Server quando si distribuisce VoIP aziendale. Per rendere Response Group disponibile agli utenti, è necessario configurare i gruppi di agenti, quindi le code e quindi i flussi di lavoro. Inoltre, un amministratore di Response Group può delegare la configurazione di un flusso di lavoro esistente a un responsabile di Response Group, che può quindi modificare e riconfigurare il flusso di lavoro e i gruppi di agenti e le code associati.

Per configurare i Response Group, è necessario essere membri di almeno uno dei ruoli amministrativi seguenti:

|**Gruppo di sicurezza Active Directory (1)** <br/> |Creare flusso di lavoro  <br/> |Assegnare responsabile  <br/> |Creare/assegnare agenti, code  <br/> |Creare/gestire festività e orari di ufficio  <br/> |Attivare/disattivare il flusso di lavoro  <br/> |Configurare il flusso di lavoro (IVR o gruppo di risposta)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√(2)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |

> [!NOTE]
> **(1)** Un oggetto utente di Servizi di dominio Active Directory deve essere membro del gruppo di sicurezza di Active Directory specificato elencato. Un amministratore o un altro membro delegato del gruppo di Active Directory con le autorizzazioni appropriate per aggiungere utenti a un gruppo di sicurezza (ad esempio, Amministratore, Operatori account) deve aggiungere un oggetto utente al gruppo o al gruppo di sicurezza elencato per consentire all'utente di eseguire le funzioni elencate. **(2) Solo** per i flussi di lavoro assegnati da CsResponseGroupAdministrator a CsResponseGroupManager. **(3) Un** responsabile di Response Group può assegnare un altro membro di CsResponseGroupManager a un flusso di lavoro già gestito dal manager corrente. **(4)** CsViewOnlyAdministrator può eseguire solo cmdlet di verbo "Get".

## <a name="response-group-configuration-prerequisites"></a>Prerequisiti di configurazione di Response Group

Per Response Group sono necessari i componenti seguenti:

- Servizio applicazione

- Applicazione Response Group

- Language Pack

- Archivio file (per gestire i file audio)

- Servizi Web (include lo strumento di configurazione di Response Group e la console di accesso e disconnessione degli agenti)

Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.

Prima di configurare Response Group, potrebbe essere necessario eseguire le attività seguenti:

- Abilitare gli utenti per Lync Server 2013 e VoIP aziendale.

- Modificare un file di configurazione in modo che sia conforme agli standard FIPS (Federal Information Processing Standard).

- Modificare le regole di confronto del database per supportare caratteri Yi, Meng e Zang per i nomi di code e i nomi dei gruppi di agenti.

### <a name="enabling-users"></a>Abilitazione degli utenti

Il primo passaggio nella configurazione di Response Group consiste nel creare gruppi di agenti. Prima di creare un gruppo di agenti, è necessario abilitare gli utenti che saranno agenti per Response Group per Skype for Business e VoIP aziendale. L'abilitazione Skype for Business utenti è in genere un passaggio nella distribuzione edizione Enterprise server edizione Standard server. Per informazioni dettagliate sull'abilitazione degli utenti Skype for Business, vedere [Enable or Disable Users for Lync Server 2013 Preview.](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server) L'abilitazione degli utenti per VoIP aziendale è in genere un passaggio della distribuzione di VoIP aziendale. Per informazioni dettagliate, vedere [Enable users for VoIP aziendale in Skype for Business Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Conformità ai requisiti FIPS

Fare riferimento a questa sezione solo se l'organizzazione deve essere conforme agli standard FIPS (Federal Information Processing Standards).

Per essere conformi a FIPS, è necessario modificare il file Web.config a livello dell'applicazione in modo da usare un algoritmo di crittografia diverso dopo aver installato Servizi Web. È necessario specificare l'uso dell'algoritmo 3DES (Triple Data Encryption Standard) per ASP.NET per l'elaborazione dei dati sugli stati di visualizzazione. Per l'applicazione Response Group, questo requisito si applica a Response Group Configuration Tool e alla console di accesso e disconnessione dell'agente. Per informazioni dettagliate su questo requisito, vedere l'articolo 911722 della Microsoft Knowledge Base "È possibile che venga visualizzato un messaggio di errore quando si accede alle pagine Web di ASP.NET con ViewState abilitato dopo l'aggiornamento da ASP.NET 1.1 a ASP.NET 2.0", all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183) .

Per modificare il file Web.config, eseguire le operazioni seguenti:

1. In un editor di testo come Blocco note aprire il file Web.config a livello dell'applicazione.

2. Nel file Web.config individuare la  `<system.web>` sezione.

3. Aggiungi la sezione  `<machineKey>` seguente a nella `<system.web>` sezione:

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Salvare il file Web.config.

5. Riavviare il Internet Information Services (IIS) eseguendo il comando seguente al prompt dei comandi:

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Supporto di caratteri Yi, Meng e Zang

Fare riferimento a questa sezione solo se l'organizzazione richiede il supporto di caratteri Yi, Meng o Zang.

> [!NOTE]
> Per informazioni sui caratteri Yi, Meng e Zang e sul motivo per cui potrebbero essere importanti per la distribuzione, vedere le informazioni sui set di caratteri GB18030. [https://go.microsoft.com/fwlink/p/?linkId=240223](/previous-versions/sql/sql-server-2008-r2/ms180991(v=sql.105))

Per il supporto di caratteri Yi, Meng o Zang è necessario modificare le regole di confronto del database Rgsconfig. Modificare le regole di confronto della colonna **Name** nelle tabelle seguenti di ogni database Rgsconfig:

- dbo. AgentGroups

- dbo. BusinessHours

- dbo. HolidaySets

- dbo. Code

- dbo. Flussi di lavoro

Per SQL Server 2008 R2 e SQL Server 2012, utilizzare le regole di confronto Latin_General_100 (accentati). Se si utilizzano queste regole di confronto, la distinzione tra maiuscole e minuscole non viene applicata ad alcun nome di oggetto.

È possibile modificare le regole di confronto utilizzando Microsoft SQL Server Management Studio. Per informazioni dettagliate sull'utilizzo di questo strumento, vedere ["Utilizzo di SQL Server Management Studio"](/sql/ssms/sql-server-management-studio-ssms). Per modificare le regole di confronto, eseguire la procedura seguente:

1. Verificare che SQL Server Management Studio sia configurato per consentire modifiche che richiedono la ricreazione di tabelle. Per informazioni dettagliate, vedere "Finestra di dialogo Salva [(non consentito) ".](/sql/ssms/visual-db-tools/save-not-permitted-dialog-box) Per informazioni dettagliate sull'impostazione delle regole di confronto delle colonne, vedere "Procedura: Impostazione delle regole di confronto delle colonne [(Visual Database Tools)"](/previous-versions/sql/sql-server-2008-r2/ms187473(v=sql.105)).

2. Utilizzando Microsoft SQL Server Management Studio connettersi al database Rgsconfig.

3. Trovare la tabella che si desidera modificare nel database Rgsconfig, fare clic con il pulsante destro del mouse sulla tabella e quindi scegliere **Progetta**.

4. Modificare le regole di confronto della colonna **Name** e salvare la tabella.

## <a name="response-group-deployment-steps"></a>Passaggi di distribuzione di Response Group

**Processo di distribuzione di Response Group**

|**Fase**|**Procedura**|**Autorizzazioni**|**Documentazione relativa alla distribuzione**|
|:-----|:-----|:-----|:-----|
|Abilitare gli utenti per Skype for Business e per VoIP aziendale  <br/> |Abilitare gli utenti che saranno agenti per Skype for Business e VoIP aziendale. Gli utenti devono essere abilitati per poter essere aggiunti a gruppi di agenti. In genere, gli utenti sono abilitati Skype for Business durante la edizione Enterprise o edizione Standard server. Gli utenti sono abilitati per VoIP aziendale durante la VoIP aziendale distribuzione.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Abilitare o disabilitare gli utenti per Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server) <br/> [Abilitare gli utenti per VoIP aziendale in Skype for Business Server](enable-users-for-enterprise-voice.md) <br/> |
|Creazione e configurazione di Response Group, costituiti da gruppi di agenti, code e flussi di lavoro  <br/> |1. Utilizzare il Skype for Business Server o Skype for Business Server Management Shell per eseguire le operazioni seguenti:  <br/> a. Creare e configurare gruppi di agenti.  <br/> b. Creare e configurare code.  <br/> 2. Facoltativamente, utilizzare Skype for Business Server Management Shell per creare orari di ufficio e festività di Response Group predefiniti.  <br/> 3. Utilizzare lo strumento di configurazione di Response Group o Skype for Business Server Management Shell per creare flussi di lavoro (gruppi di risposta o flussi di chiamate IVR), inclusi orari di ufficio e festività di Response Group personalizzati.  <br/> È possibile accedere a Strumento di configurazione di Response Group Skype for Business Server Pannello di controllo.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Creare gruppi di agenti per Response Group](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-agent-groups) <br/> [Creare code di Response Group](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-queues) <br/> [(Facoltativo) Definire l'orario di ufficio di Response Group in Skype for Business](optional-define-response-group-business-hours.md) <br/> [(Facoltativo) Definire i set di festività di Response Group in Skype for Business](optional-define-response-group-holiday-sets.md) <br/> [Progettazione e creazione di flussi di lavoro di Response Group in Skype for Business](designing-and-creating-response-group-workflows.md) <br/> |
|(Facoltativo) Personalizzazione delle impostazioni a livello di applicazione  <br/> |Utilizzare Skype for Business Server Management Shell per personalizzare la configurazione predefinita di musica in attesa, il file audio di musica in attesa predefinito, il periodo di tolleranza di ringback dell'agente e la configurazione del contesto di chiamata.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Gestione delle impostazioni di Response Group a livello di applicazione in Skype for Business](managing-application-level-response-group-settings.md) <br/> |
|(Facoltativo) Delega della gestione dei Response Group  <br/> |Assegnare agli utenti il ruolo CsResponseGroupManager per delegare la configurazione dei Response Group. I responsabili di Response Group possono quindi configurare i Response Group a loro assegnati.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Pianificazione del controllo di accesso basato sui ruoli](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) <br/> |
|Verificare la distribuzione di Response Group  <br/> |Testare la risposta alle chiamate nei flussi di lavoro del gruppo di risposta e del sistema IVR per assicurare che la configurazione funzioni come previsto.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Panoramica degli scenari di creazione di flussi di lavoro

Quando si creano flussi di lavoro, i possibili scenari sono due:

- **L'amministratore crea e configura il flusso di lavoro** - Il membro del ruolo CsResponseGroupAdministrator (o equivalente) crea e attiva il flusso di lavoro e tutti i relativi elementi, ad esempio gruppi di agenti, code, festività, orario di ufficio, musica di attesa e così via.

- **L'amministratore crea il flusso di lavoro e il manager configura le opzioni** - Il membro del ruolo CsResponseGroupAdministrator (o equivalente) definisce l'URI SIP primario, assegna uno o più membri al ruolo CsResponseGroupManager, quindi seleziona una coda e attiva il flusso di lavoro. Il membro del ruolo CsResponseGroupManager può quindi effettuare l'accesso e modificare la configurazione del flusso di lavoro creando gruppi di agenti. Assegna inoltre il gruppo alla coda, configurando il numero di telefono, festività, orario di ufficio, musica di attesa e così via.

    > [!NOTE]
    > Se si vuole creare un flusso di lavoro gestito è necessario crearlo come attivo. Dopo aver salvato un flusso di lavoro gestito e attivo, sarà possibile modificarlo e disattivarlo.