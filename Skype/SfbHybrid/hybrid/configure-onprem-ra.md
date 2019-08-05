---
title: Configurare un account di risorse in Skype for Business Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: configurare un account delle risorse per Skype for Business Server 2019.
ms.openlocfilehash: 33211f7dcd56e402167a3c810343947d4dfe0954
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "36185546"
---
# <a name="configure-resource-accounts"></a>Configurare gli account delle risorse

Le implementazioni ibride di Skype for Business Server 2019 usano solo i servizi cloud forniti dal sistema telefonico per la messaggistica unificata e non si integrano con Exchange Online. In Skype for Business Server 2019 ora è possibile usare le code di chiamata cloud e gli operatori automatici descritti in [Ecco cosa si ottiene con il sistema telefonico in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Per usare questi servizi di sistema telefonico con Skype for Business Server 2019, è necessario creare account di risorse che fungono da endpoint dell'applicazione e possono essere assegnati numeri di telefono, quindi usare l'interfaccia di amministrazione di Team online per configurare la coda di chiamata o l'operatore automatico. Questo account delle risorse può essere ospitato online (vedere [gestire gli account delle risorse in Microsoft teams](/MicrosoftTeams/manage-resource-accounts) per creare gli account delle risorse ospitati online) o locali come descritto in questo articolo. In genere si avranno più nodi del servizio di sistema telefonico, ognuno dei quali è mappato a un account di risorse, che può essere ospitato online o in Skype for Business Server 2019.

Se si ha un operatore automatico di messaggistica unificata di Exchange e un sistema di accodamento delle chiamate, prima di passare a Exchange Server 2019 o Exchange Online è necessario registrare manualmente i dettagli come descritto di seguito e quindi implementare un sistema completamente nuovo con l'interfaccia di amministrazione di Teams .

## <a name="overview"></a>Panoramica

Se il servizio di sistema telefonico richiede un numero di servizio, le varie dipendenze possono essere soddisfatte nella sequenza seguente:

1. Ottenere un numero di servizio
2. Acquistare una licenza per il sistema telefonico
3. Creare l'account delle risorse. Per avere un account di risorse associato è necessario un operatore automatico o una coda di chiamata.
4. Attendere la sincronizzazione di Active Directory tra online e in locale
5. Assegnare la licenza di sistema telefonico all'account delle risorse.
6. Assegnare un numero di servizio all'account delle risorse.
7. Creare un servizio di sistema telefonico (una coda di chiamata o un operatore automatico)
8. Associare l'account delle risorse a un servizio: (New-CsApplicationInstanceAssociation)

Se l'operatore automatico o la coda di chiamata è annidata in un operatore automatico di primo livello, l'account di risorse associato deve avere solo un numero di telefono se si vogliono più punti di entrata nella struttura degli operatori automatici e delle code di chiamata.

Per reindirizzare le chiamate alle persone dell'organizzazione ospitate online, devono avere una licenza per il **sistema telefonico** ed essere abilitate per Enterprise Voice o avere piani di chiamata di Office 365. Vedere [assegnare le licenze di Microsoft teams](/MicrosoftTeams/assign-teams-licenses). Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell. Ad esempio, eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Se il servizio di sistema telefonico che si sta creando sarà annidato e non sarà necessario un numero di telefono, il processo sarà:

1. Creare l'account delle risorse  
2. Attendere la sincronizzazione di Active Directory tra online e in locale
3. Creare un servizio di sistema telefonico
4. Associare l'account delle risorse a un servizio di sistema telefonico

## <a name="create-a-resource-account-with-a-phone-number"></a>Creare un account delle risorse con un numero di telefono

La creazione di un account delle risorse che usa un numero di telefono richiede l'esecuzione delle attività seguenti nell'ordine seguente:

1. Porta o ottenere un numero di servizio gratuito o a pagamento. Il numero non può essere assegnato ad altri account di servizi vocali o risorse.

   Prima di assegnare un numero di telefono a un account delle risorse, è necessario ottenere o trasferire i numeri di servizio a pagamento o a numero verde esistenti. Dopo aver ottenuto il numero di telefono o i numeri di servizio gratuiti, verranno visualizzati nei numeri di telefono della**segreteria** > **telefonica**di **Microsoft teams** > e il **tipo di numero** elencato verrà elencato come **servizio gratuito**. Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono](/MicrosoftTeams/getting-service-phone-numbers) o se si vuole trasferire un numero di servizio esistente, vedere trasferire i [numeri di telefono in Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).

   Se si è al di fuori degli Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft teams per ottenere i numeri di servizio. Vai a [gestire i numeri di telefono per l'organizzazione](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) per vedere come farlo dall'esterno degli Stati Uniti.

2. Acquistare una licenza di sistema telefonico. Vedere  
   - [Office 365 Enterprise E1 e E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Software aziendale di Office 365 Enterprise E5](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Creare un account di risorse locale eseguendo il `New-CsHybridApplicationEndpoint` cmdlet per ogni servizio di sistema telefonico e assegnargli un nome, un indirizzo SIP e così via.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Per altre informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

4. Opzionale Dopo aver creato gli account delle risorse, è possibile attendere la sincronizzazione di un annuncio tra online e in locale oppure forzare una sincronizzazione e procedere alla configurazione online dei servizi di sistema telefonico. Per forzare una sincronizzazione, eseguire il comando seguente nel computer che esegue AAD Connect (se non lo si è già fatto, è necessario caricarlo `import-module adsync` per eseguire il comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Per altre informazioni su questo comando, vedere [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .

5. Assegnare la licenza di sistema telefonico all'account delle risorse. Vedere [assegnare licenze di Microsoft teams](/MicrosoftTeams/assign-teams-licenses) e [assegnare licenze a un solo utente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).

    Se si sta assegnando un numero di telefono a un account di risorse, è ora possibile usare la licenza per gli utenti virtuali del sistema telefonico senza costi. In questo modo le funzionalità del sistema telefonico sono disponibili per i numeri di telefono a livello di organizzazione e consentono di creare funzionalità di operatore automatico e coda di chiamata.


6. Assegnare il numero di servizio all'account delle risorse. Usare il `Set-CsHybridApplicationEndpoint` comando per assegnare un numero di telefono (con l'opzione-LineUri) all'account delle risorse.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Per altre informazioni su questo comando, vedere [set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) .

    Per assegnare un routing diretto o un numero ibrido a un account delle risorse, usare il cmdlet seguente:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

L'account delle risorse avrà bisogno di un numero di telefono assegnato se verrà assegnato a un operatore automatico di primo livello o a una coda di chiamata. I numeri di telefono degli utenti (abbonati) non possono essere assegnati a un account delle risorse, ma possono essere usati solo numeri di telefono a pagamento o a numero verde.

    You can assign a Direct Routing Hybrid number to your resource account.  See [Plan Direct Routing](direct-routing-plan) for details.

    > [!NOTE]
    > Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.

    > [!NOTE]
    > Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.

7. Creare il servizio di sistema telefonico. Vedere una delle opzioni seguenti:

   - [Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Associare l'account delle risorse al servizio di sistema telefonico scelto in precedenza.

Un esempio di implementazione di piccole imprese è disponibile in [Small Business example-configurare un operatore automatico](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) e un [esempio di piccola impresa-configurare una coda di chiamata](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).

## <a name="create-a-resource-account-without-a-phone-number"></a>Creare un account delle risorse senza un numero di telefono

Questa sezione illustra la creazione di un account delle risorse ospitato in locale. La creazione di un account delle risorse ospitato online viene discussa in [gestire gli account delle risorse in Microsoft teams](/MicrosoftTeams/manage-resource-accounts).

Questi passaggi sono necessari se si sta creando un nuovo sistema di servizio di sistema telefonico o una struttura di ricompilazione creata originariamente nella messaggistica unificata di Exchange.

Accedere al server front-end Skype for business ed eseguire i cmdlet di PowerShell seguenti:

1. Creare un account di risorse locale eseguendo il `New-CsHybridApplicationEndpoint` cmdlet per ogni servizio di sistema telefonico e assegnargli un nome, un indirizzo SIP e così via.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Per altre informazioni su questo comando, vedere [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .

2. Opzionale Dopo aver creato gli account delle risorse, è possibile attendere la sincronizzazione di un annuncio tra online e in locale oppure forzare una sincronizzazione e procedere alla configurazione online dei servizi di sistema telefonico. Per forzare una sincronizzazione, eseguire il comando seguente nel computer che esegue AAD Connect (se non lo si è già fatto, è necessario caricarlo `import-module adsync` per eseguire il comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Per altre informazioni su questo comando, vedere [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) .

3. Creare il servizio di sistema telefonico. Vedere una delle opzioni seguenti:
   - [Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Associare l'account delle risorse e il servizio di sistema telefonico scelto in precedenza.

Un esempio di implementazione di piccole imprese è disponibile in [Small Business example-configurare un operatore automatico](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) e un [esempio di piccola impresa-configurare una coda di chiamata](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).

## <a name="test-the-implementation"></a>Testare l'implementazione

Il modo migliore per testare l'implementazione consiste nel chiamare il numero configurato per un servizio di sistema telefonico e connettersi a uno degli agenti o dei menu. È anche possibile inserire rapidamente una chiamata di prova usando il **pulsante test** nel riquadro azioni dell'interfaccia di amministrazione. Se si vogliono apportare modifiche a un servizio di sistema telefonico, selezionarlo e quindi nel riquadro azioni fare clic su **modifica**.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Spostamento di un operatore automatico di Exchange UM o di una coda di chiamata nel sistema telefonico

La migrazione dalla messaggistica unificata di Exchange al sistema telefonico richiede la ricreazione della struttura della coda di chiamata e dell'operatore automatico, che esegue direttamente la migrazione da una a un'altra non è supportata. Per implementare di nuovo un set di code di chiamata e operatori automatici:

1. Ottenere un elenco di tutti gli operatori automatici di messaggistica unificata di Exchange e delle code di chiamata eseguendo il comando seguente nel sistema Exchange 2013 o 2016 durante l'accesso come amministratore:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Per ogni coda di messaggistica unificata di Exchange o l'operatore automatico, annotarne la posizione nella struttura, le impostazioni e ottenere copie di file audio o di sintesi vocale associati (il GUID nell'output sarà il nome di una cartella in cui sono archiviati i file). Per ottenere questi dettagli, è possibile eseguire il comando:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Per altre informazioni su questo comando, vedere [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) . Un elenco completo delle opzioni che potrebbe essere necessario acquisire è presso [i membri di UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) , ma le opzioni più importanti da notare sono:

    - Orari di ufficio
    - Orari non lavorativi
    - Lingua
    - Calendario festività

3. Creare nuovi endpoint locali come descritto in precedenza.
   Assegnare all'operatore automatico di primo livello un numero temporaneo per scopi di test.

4. Configurare un servizio di sistema telefonico che usa gli endpoint come descritto in precedenza.

   Potrebbe essere utile usare gli esercizi nell'esempio di esercitazione intitolato [Small Business-configurare un operatore automatico](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) per creare una mappa logica delle gerarchie nel vecchio sistema di messaggistica unificata di Exchange.
5. Testare il servizio di sistema telefonico.
6. Riassegnare il numero di telefono collegato alla coda di chiamata di messaggistica unificata di Exchange o all'operatore automatico al servizio di sistema telefonico corrispondente.  

   A questo punto, se è già stata eseguita la migrazione della segreteria telefonica di messaggistica unificata, è necessario essere in grado di eseguire la migrazione a Exchange Server 2019.

## <a name="see-also"></a>Vedere anche

[Creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue)

[Cosa sono gli operatori automatici cloud?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurare un operatore automatico cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Pianificare gli operatori automatici del cloud](plan-cloud-auto-attendant.md)

[Pianificare le code delle chiamate cloud](plan-call-queue.md)

[Pianificare il servizio cloud Voicemail per gli utenti locali](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Gestire gli account delle risorse in Microsoft teams](/MicrosoftTeams/manage-resource-accounts) - \(per creare account risorse ospitati online\)
