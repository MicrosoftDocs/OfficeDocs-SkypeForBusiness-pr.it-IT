---
title: Processo di distribuzione per Response Group in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Processo di distribuzione e procedura per il gruppo di risposte in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 62c6471018c3c1c6d1943d252975d2e671ef8cf4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187343"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Processo di distribuzione per Response Group in Skype for business

Processo di distribuzione e procedura per il gruppo di risposte in Skype for Business Server VoIP aziendale.

Response Group è una funzionalità VoIP aziendale che instrada e accoda le chiamate in arrivo a gruppi di persone, detti agenti, ad esempio un help desk o un servizio di assistenza clienti.

I componenti necessari per il gruppo di risposte sono installati e abilitati automaticamente nel server front-end o Standard Edition quando si distribuisce VoIP aziendale. Per rendere disponibile un gruppo di risposte agli utenti, è necessario configurare i gruppi di agenti, le code e quindi i flussi di lavoro. Inoltre, un amministratore del gruppo di risposte può delegare la configurazione di un flusso di lavoro esistente a un responsabile del gruppo di risposte, che può quindi modificare e riconfigurare il flusso di lavoro e i gruppi e le code dell'agente associato.

Per configurare i Response Groups, è necessario essere membri di almeno uno dei ruoli amministrativi seguenti:

|**Gruppo di sicurezza di Active Directory (1)** <br/> |Creare un flusso di lavoro  <br/> |Assegna Manager  <br/> |Creare agenti/Assign, code  <br/> |Creare/gestire le festività e le ore lavorative  <br/> |Attivare/disattivare il flusso di lavoro  <br/> |Configurare il flusso di lavoro (IVR o gruppo di caccia)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√ (2)  <br/> |√ (3)  <br/> |√ (3)  <br/> |√ (3)  <br/> |√ (3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |

> [!NOTE]
> **(1)** un oggetto utente di servizi di dominio Active Directory deve essere un membro del gruppo di sicurezza Active Directory specificato elencato. Un amministratore o un altro membro del gruppo di Active Directory delegato con le autorizzazioni appropriate per aggiungere utenti a un gruppo di sicurezza, ad esempio Administrator, account Operators, deve aggiungere un oggetto utente al gruppo di sicurezza o al gruppo di protezione elencato per consentire all'utente di eseguire le funzioni elencate. **(2)** solo per i flussi di lavoro assegnati da CsResponseGroupAdministrator a CsResponseGroupManager. **(3)** un responsabile del gruppo di risposte può assegnare un altro membro di CsResponseGroupManager a un flusso di lavoro già gestito da gestione corrente. **(4)** CsViewOnlyAdministrator può eseguire solo i cmdlet "Get" del verbo.

## <a name="response-group-configuration-prerequisites"></a>Prerequisiti per la configurazione di Response Group

Response Group richiede i componenti seguenti:

- Servizio applicazione

- Response Group Application

- Language Pack

- Archivio file (per contenere i file audio)

- Servizi Web (include lo strumento di configurazione di Response Group e la console di accesso e disconnessione degli agenti)

Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.

Potrebbe essere necessario eseguire le attività seguenti prima di configurare Response Group:

- Consentire agli utenti di Lync Server 2013 e Enterprise Voice.

- Modificare un file di configurazione per essere conforme alle norme FIPS (Federal Information Processing Standards).

- Modificare le regole di confronto del database per supportare i caratteri Yi, Meng e Zang per i nomi delle code e i nomi dei gruppi di agenti.

### <a name="enabling-users"></a>Abilitazione degli utenti

Il primo passaggio della configurazione di Response Group consiste nel creare gruppi di agenti. Prima di poter creare un gruppo di agenti, è necessario abilitare gli utenti che saranno agenti per Response Group per Skype for business e Enterprise Voice. L'abilitazione degli utenti per Skype for business è in genere un passaggio nel server Enterprise Edition o nella distribuzione di server Standard Edition. Per informazioni dettagliate sull'abilitazione degli utenti per Skype for business, vedere [abilitare o disabilitare gli utenti per Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). L'abilitazione degli utenti per VoIP aziendale è in genere un passaggio nella distribuzione di VoIP aziendale. Per informazioni dettagliate, vedere [abilitare gli utenti per VoIP aziendale in Skype for Business Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Conformità ai requisiti FIPS

Questa sezione si applica solo se l'organizzazione deve essere conforme alle norme FIPS (Federal Information Processing Standards).

Per essere conformi con FIPS, è necessario modificare il file Web. config a livello di applicazione per usare un algoritmo di crittografia diverso dopo l'installazione dei servizi Web. Devi specificare che ASP.NET usa l'algoritmo 3DES (Triple Data Encryption Standard) per elaborare i dati sullo stato di visualizzazione. Per l'applicazione Response Group, questo requisito si applica allo strumento di configurazione dei gruppi di risposta e alla console di accesso e disconnessione dell'agente. Per informazioni dettagliate su questo requisito, vedere l'articolo 911722 della Microsoft Knowledge Base "potrebbe essere visualizzato un messaggio di errore quando si accede alle pagine Web di ASP.NET che hanno ViewState abilitato dopo l'aggiornamento da ASP.NET 1,1 a ASP.NET [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)2,0".

Per modificare il file Web. config, eseguire le operazioni seguenti:

1. In un editor di testo, ad esempio Blocco note, aprire il file Web. config a livello di applicazione.

2. Nel file Web. config individuare la `<system.web>` sezione.

3. Aggiungere la sezione `<machineKey>` seguente alla `<system.web>` sezione:

   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Salvare il file Web. config.

5. Riavviare il servizio Internet Information Services (IIS) eseguendo il comando seguente al prompt dei comandi:

   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Supporto di caratteri Yi, Meng e Zang

Questa sezione si applica solo se l'organizzazione deve supportare i caratteri Yi, Meng o Zang.

> [!NOTE]
> Per informazioni sui caratteri di Yi, Meng e Zang e sul motivo per cui potrebbero essere importanti per la distribuzione, vedere le informazioni sui set [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)di caratteri GB18030.

Per supportare i caratteri Yi, Meng o Zang, è necessario modificare le regole di confronto per il database rgsconfig. Modificare le regole di confronto della colonna **Name** nelle tabelle seguenti in ogni database di rgsconfig:

- dbo. AgentGroups

- dbo. BusinessHours

- dbo. HolidaySets

- dbo. Code

- dbo. Flussi

Per SQL Server 2008 R2 e SQL Server 2012, usare le regole di confronto Latin_General_100 (accento sensibile). Se si usano queste regole di confronto, tutti i nomi degli oggetti non saranno distinzione tra maiuscole e minuscole.

È possibile modificare le regole di confronto tramite Microsoft SQL Server Management Studio. Per informazioni dettagliate sull'uso di questo strumento, vedere ["utilizzo di SQL Server Management Studio"](https://go.microsoft.com/fwlink/p/?linkId=196184). Seguire questa procedura per modificare le regole di confronto:

1. Verificare che SQL Server Management Studio sia configurato in modo da consentire la ricreazione delle modifiche che richiedono le tabelle. Per informazioni dettagliate, vedere la finestra di [dialogo "Salva (non consentita)"](https://go.microsoft.com/fwlink/p/?linkId=196186). Per informazioni dettagliate sull'impostazione di regole di confronto delle colonne, vedere ["procedura: impostare le regole di confronto delle colonne (Visual Database Tools)"](https://go.microsoft.com/fwlink/p/?linkId=196185).

2. Con Microsoft SQL Server Management Studio connettersi al database di rgsconfig.

3. Individuare la tabella che si vuole modificare nel database di rgsconfig, fare clic con il pulsante destro del mouse sulla tabella e scegliere **progettazione**.

4. Modificare le regole di confronto della colonna **nome** e salvare la tabella.

## <a name="response-group-deployment-steps"></a>Passaggi per la distribuzione di Response Group

**Processo di distribuzione di Response Group**

|**Fase**|**Passaggi**|**Autorizzazioni**|**Documentazione di distribuzione**|
|:-----|:-----|:-----|:-----|
|Abilitare gli utenti per Skype for business e per Enterprise Voice  <br/> |Abilitare gli utenti che saranno agenti per Skype for business e Enterprise Voice. Gli utenti devono essere abilitati prima di poterli aggiungere ai gruppi di agenti. In genere, gli utenti sono abilitati per Skype for business durante la distribuzione di Enterprise Edition o Standard Edition Server. Gli utenti sono abilitati per VoIP aziendale durante la distribuzione di VoIP aziendale.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Abilitare o disabilitare gli utenti per Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Consentire agli utenti di VoIP aziendale in Skype for Business Server](enable-users-for-enterprise-voice.md) <br/> |
|Creare e configurare Response Groups, costituiti da gruppi di agenti, code e flussi di lavoro  <br/> |1. usare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per eseguire le operazioni seguenti:  <br/> un. Creare e configurare gruppi di agenti.  <br/> b. Creare e configurare le code.  <br/> 2. Facoltativamente, usare Skype for Business Server Management Shell per creare orari di lavoro e festività predefiniti per i gruppi di risposte.  <br/> 3. usare lo strumento di configurazione di Response Group o Skype for Business Server Management Shell per creare flussi di lavoro (gruppi di risposta o flussi di chiamate IVR), tra cui le ore lavorative e le festività dei gruppi di risposta personalizzati.  <br/> È possibile accedere allo strumento di configurazione del Response Group tramite il pannello di controllo di Skype for Business Server.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Creare gruppi di agenti di Response Group](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Creare code di Response Group](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [Opzionale Definire le ore lavorative del gruppo di risposta in Skype for business](optional-define-response-group-business-hours.md) <br/> [Opzionale Definire set di festività di Response Group in Skype for business](optional-define-response-group-holiday-sets.md) <br/> [Progettazione e creazione di flussi di lavoro di Response Group in Skype for business](designing-and-creating-response-group-workflows.md) <br/> |
|Opzionale Personalizzare le impostazioni a livello di applicazione  <br/> |Usare Skype for Business Server Management Shell per personalizzare la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in attesa, il periodo di richiamata dell'agente e la configurazione del contesto delle chiamate.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Gestione delle impostazioni dei gruppi di risposte a livello di applicazione in Skype for business](managing-application-level-response-group-settings.md) <br/> |
|Opzionale Gestione dei delegati di Response Groups  <br/> |Assegna agli utenti il ruolo CsResponseGroupManager per delegare la configurazione dei gruppi di risposta. I responsabili del gruppo di risposte possono quindi configurare i gruppi di risposte assegnati.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Pianificazione per il controllo dell'accesso basato sui ruoli](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Verificare la distribuzione di Response Group  <br/> |Provare a rispondere alle chiamate al gruppo di ricerca e ai flussi di lavoro di risposta vocale interattivi per verificare che la configurazione funzioni come previsto.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Panoramica degli scenari di creazione del flusso di lavoro

Quando si creano flussi di lavoro, esistono due scenari possibili:

- **L'amministratore crea e configura il flusso di lavoro** , ovvero il membro del ruolo CsResponseGroupAdministrator (o equivalente) crea e attiva il flusso di lavoro e tutti gli elementi del flusso di lavoro, ad esempio i gruppi di agenti, le code, le festività e gli orari di ufficio, musica in attesa e così via.

- **L'amministratore crea il flusso di lavoro e il responsabile configura le opzioni** , ovvero il membro del ruolo CsResponseGroupAdministrator (o equivalente) definisce l'URI SIP principale, il nome visualizzato, assegna un membro o i membri del ruolo CsResponseGroupManager e Seleziona una coda e attiva il flusso di lavoro. CsResponseGroupManager può quindi eseguire l'accesso e modificare la configurazione del flusso di lavoro creando gruppi di agenti e assegnando anche il gruppo alla coda, configurando il numero di telefono, le festività e le ore lavorative, la musica in attesa e così via.

    > [!NOTE]
    > Quando si vuole creare un flusso di lavoro gestito, è necessario creare il flusso di lavoro come attivo. Dopo aver salvato un flusso di lavoro attivo e gestito, è possibile modificare e disattivare il flusso di lavoro.


