---
title: Creare una coda di chiamata
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Informazioni su come configurare il sistema telefonico per le code delle chiamate cloud con Microsoft teams.
ms.openlocfilehash: b49684d230f63c741287ee0e0b24e32bd134834d
ms.sourcegitcommit: 101fc98da3e8e969652ec1aca77dd4d7aef4a918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "36185002"
---
# <a name="create-a-cloud-call-queue"></a>Creare una coda di chiamata cloud

Le code delle chiamate cloud sono un servizio che riproduce un saluto alle chiamate del cliente prima di inserirle in una coda durante la ricerca tra un set predefinito di agenti per rispondere a queste chiamate. È possibile creare code di chiamata singole o multiple per l'organizzazione.
  
Le code delle chiamate cloud possono essere fornite:
  
- Messaggio di saluto.
- Musica mentre le persone sono in attesa.
- Reindirizzamento delle chiamate agli agenti di chiamata nelle liste di distribuzione e nei gruppi di sicurezza abilitati alla posta elettronica.
- Impostazioni parametri diversi, ad esempio la dimensione massima della coda, il timeout e le opzioni di gestione delle chiamate.

Quando qualcuno chiama un numero di telefono associato a una coda di chiamata tramite un [account delle risorse](manage-resource-accounts.md), si sente prima un saluto (se è configurato), quindi verrà inserito nella coda e attenderà l'agente di chiamata disponibile successivo. La persona che effettua una chiamata sente la musica mentre è in attesa e le chiamate verranno offerte agli agenti di chiamata in ordine *First in, First out* (FIFO).
  
Tutte le chiamate in attesa nella coda verranno distribuite usando uno dei metodi seguenti:
  
- Con il routing di Attendant, la prima chiamata nella coda suonerà tutti gli agenti contemporaneamente.
- Con l'instradamento seriale, la prima chiamata della squillerà a tutti gli agenti di chiamata uno alla volta.
- Con Round Robin, il routing delle chiamate in arrivo è bilanciato in modo che ogni agente di chiamata otterrà lo stesso numero di chiamate dalla coda.

    > [!NOTE]
    > Gli agenti di chiamata **offline**, hanno impostato la loro presenza **** su non disturbare o hanno scelto di non ricevere chiamate nella coda di chiamata.
  
- Solo una notifica di chiamata in arrivo (per la chiamata in cima alla coda) per volta viene inviata agli agenti di chiamata.
- Una volta che un agente di chiamata accetta la chiamata, la prossima chiamata in arrivo in coda viene segnalata agli agenti di chiamata.

> [!NOTE]
> Questo articolo si applica sia a Microsoft teams che a Skype for business online.

## <a name="step-1---get-started"></a>Passaggio 1-per iniziare

Per iniziare a utilizzare le code di chiamata, è importante ricordare quanto segue.
  
- È necessaria una coda di chiamata per avere un account di risorse associato. Per informazioni dettagliate sugli account delle risorse, vedere [gestire gli account delle risorse in teams](manage-resource-accounts.md) .
- Se si sta assegnando un numero di telefono a un account di risorse, è ora possibile usare la licenza per gli [utenti virtuali](teams-add-on-licensing/virtual-user.md)del sistema telefonico senza costi. In questo modo le funzionalità del sistema telefonico sono disponibili per i numeri di telefono a livello di organizzazione e consentono di creare servizi di operatore automatico e coda di chiamata.

> [!NOTE]
> I numeri di servizio di routing diretto per le code di chiamata sono supportati solo per gli utenti e gli agenti di Microsoft teams.

> [!NOTE]
> Per reindirizzare le chiamate alle persone dell'organizzazione online, devono avere una licenza per il **sistema telefonico** e essere abilitate per VoIP aziendale o avere piani di chiamata di Office 365. Vedere [assegnare licenze di Skype for business](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [assegnare licenze di Microsoft teams](assign-teams-licenses.md). Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell. Ad esempio, eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per altre informazioni sui piani di chiamate di Office 365, vedere [sistemi di telefonia e](calling-plan-landing-page.md) piani di chiamata e [piani di chiamata per Office 365](calling-plans-for-office-365.md).

- È possibile assegnare numeri di telefono a pedaggio e a pedaggio gratuiti nell'interfaccia di **amministrazione di Microsoft teams** o trasferiti da un altro provider di servizi alle code delle chiamate cloud. Per ottenere e utilizzare i numeri gratuiti, è necessario impostare il Credito per la comunicazione.

    > [!NOTE]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati a code di chiamata, ma solo numeri di telefono di servizio a pagamento o numeri verdi.
  
- Quando si distribuiscono le chiamate in arrivo da una coda di chiamata cloud, questi client sono supportati per gli agenti di chiamata:

  - Client desktop Skype for Business 2016 (versioni a 32 e 64 bit)

  - Client desktop Lync 2013 (versioni a 32 e 64 bit)

  - Tutti i modelli di telefono IP supportati per Microsoft teams. Vedere [ottenere telefoni per Skype for business online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).

  - Client Mac Skype for Business (versione 16.8.196 e versioni successive)

  - Client Android Skype for Business (versione 6.16.0.9 e versioni successive)

  - Client iPhone Skype for Business (versione 6.16.0 e versioni successive)

  - Client Mac Skype for Business (versione 6.16.0 e versioni successive)

  - Client Microsoft Teams Windows (versioni a 32 e 64 bit)

  - Client Microsoft Teams Mac

  - App per iPhone di Microsoft Teams

  - App Microsoft teams Android

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Fase 2 - Ottenere o trasferire numeri di servizio a pagamento o a numero verde

Prima di poter creare e configurare le code di chiamata, è necessario ottenere numeri di servizio a pagamento o meno oppure  trasferire quelli esistenti. Dopo aver ottenuto i numeri di telefono del servizio a pagamento o a pedaggio, verranno visualizzati nei**numeri di telefono**della**voce** > del**portale** > dell'interfaccia di >  **amministrazione Microsoft teams**legacy e il tipo di **numero** elencato sarà elencato come **servizio a pagamento gratuito**. Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono](getting-service-phone-numbers.md) o se si vuole trasferire un numero di servizio esistente, vedere trasferire i [numeri di telefono in Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se si è al di fuori degli Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft teams per ottenere i numeri di servizio. Vai a [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per vedere come farlo dall'esterno degli Stati Uniti.

Se si stanno anche configurando gli operatori automatici, è possibile che sia necessario assegnare un numero di telefono all'account delle risorse dell'operatore automatico principale e quindi chiamarli direttamente alla coda di chiamata. In questo caso, la coda di chiamata dovrà essere creata prima di poter creare un'opzione nell'operatore automatico che seleziona la coda di chiamata.
  
## <a name="step-3---create-a-new-call-queue"></a>Passaggio 3-creare una nuova coda di chiamata

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Ogni coda di chiamata è necessaria per avere un [account di risorse](manage-resource-accounts.md)associato. Devi prima creare l'account della risorsa, quindi puoi associarlo alla coda di chiamata.

### <a name="using-the-microsoft-teams-admin-center"></a>Uso dell'interfaccia di amministrazione di Microsoft Teams

Nell'interfaccia **di amministrazione di Microsoft teams**, code di**chiamata** **vocale** >  , quindi fare clic su **+ Aggiungi nuovo**:

### <a name="set-the-call-queue-display-name-and-resource-account"></a>Impostare il nome visualizzato della coda di chiamata e l'account delle risorse

![Screenshot di una nuova coda di chiamata, con callout numerati](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![Icona del numero 1, facendo riferimento a un callout nel](media/sfbcallout1.png)
**nome** dello screenshot precedente immettere un nome visualizzato descrittivo per la coda di chiamata. È obbligatorio e può contenere fino a 64 caratteri, spazi inclusi.

 Questo nome verrà visualizzato nella notifica per la chiamata in arrivo.

* * *

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

**Aggiungere account** Selezionare un account di risorse. L'account delle risorse può o non può essere associato a un numero di telefono a pagamento o a pagamento gratuito per la coda di chiamata, ma per ogni coda di chiamata è necessario un account di risorse associato.

Se non sono presenti elenchi, è necessario ottenere i numeri di servizio e assegnarli a un account delle risorse prima di poter creare la coda di chiamata, come descritto in precedenza. Per ottenere i numeri di servizio, vedere [ottenere i numeri di telefono del servizio](getting-service-phone-numbers.md). È necessario creare un account delle risorse come descritto in [gestire gli account delle risorse in teams](manage-resource-accounts.md) se si vuole che la coda di chiamata disponga di un numero di telefono associato.

> [!NOTE]
> Se si vuole o è necessario assegnare un **dominio** , assegnarlo all'account delle risorse per la coda di chiamata.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Impostare il saluto e la musica durante l'attesa

![Screenshot delle opzioni di saluto e musica, con callout numerati](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

Il **Saluto** è opzionale. Questo è il messaggio di saluto che viene riprodotto per le persone che chiamano il numero della coda di chiamata.

È possibile caricare un file audio (formati. wav,. mp3 o. WMA).

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

**Musica in attesa** È possibile usare la musica predefinita in attesa fornita con la coda di chiamata oppure è possibile caricare un file audio in formato WAV, MP3 o WMA da usare come musica personalizzata in attesa.

* * *

### <a name="select-the-call-answering-options"></a>Selezionare le opzioni di segreteria telefonica

![Schermata delle opzioni di segreteria telefonica con callout numerati](media/5d249515-d532-4af2-90da-011404028b89.png)

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

È possibile selezionare fino a 200 gli agenti di chiamata che appartengono a una delle seguenti liste di distribuzione o gruppi:

- Gruppo Office 365
- Gruppo di sicurezza
- Elenco di distribuzione

Gli agenti di chiamata **** selezionati devono essere utenti online con licenza di **sistema telefonico** e VoIP aziendale abilitato **o** con un piano per le chiamate.

  > [!NOTE]
  > Questo vale anche se vuoi reindirizzare le chiamate agli utenti dell'organizzazione online. Questi utenti devono avere una licenza per il **sistema telefonico** e VoIP aziendale abilitato **o** avere un piano di chiamata. Per altre informazioni, vedere [assegnare licenze di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [assegnare licenze di Microsoft teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)o [quale piano per le chiamate è giusto per l'utente?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)

 Per abilitare un agente per VoIP aziendale, è possibile usare Windows PowerShell. Ad esempio, esegui:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Utenti online con una licenza di **sistema telefonico** o un piano di chiamata aggiunto a un gruppo di Office 365; una lista di distribuzione abilitata per la posta elettronica; o un gruppo di sicurezza. Per iniziare a ricevere chiamate da una coda di chiamata, potrebbero essere necessarie fino a tre ore per un nuovo agente aggiunto in una lista di distribuzione o un gruppo di sicurezza. Una lista di distribuzione o un gruppo di sicurezza appena creato può richiedere fino a 48 ore per diventare disponibile per l'uso con le code di chiamata. I Gruppi di Office 365 appena creati sono disponibili quasi immediatamente.

- Se gli agenti usano l'app Microsoft teams per ricevere chiamate in coda di chiamata, devono essere in modalità TeamsOnly.

![Screenshot del riquadro Aggiungi agenti chiamata](media/skype-for-business-add-agents-to-call-queue.png)

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

**Metodo di routing** Per il metodo di **** distribuzione delle code di chiamata, è possibile scegliere supervisore, **seriale**o **Round Robin** . Tutte le code di chiamata nuovi ed esistenti hanno l'instradamento operatore selezionato per impostazione predefinita. Quando viene usato il routing degli addetti, la prima chiamata nella coda suonerà tutti gli agenti di chiamata contemporaneamente. Il primo agente di chiamata a prendere la chiamata riceve la chiamata.

- Il **routing** degli assistenti fa sì che la prima chiamata nella coda squilli tutti gli agenti di chiamata contemporaneamente. Il primo agente di chiamata a prendere la chiamata riceve la chiamata.
- Le chiamate in arrivo di **routing seriale** suoneranno gli agenti di chiamata uno alla volta, a partire dall'inizio dell'elenco agente chiamate. Non è possibile ordinare gli agenti nell'elenco agente chiamate. Se un agente rifiuta o non seleziona una chiamata, la chiamata squillerà all'agente successivo nell'elenco e cercherà tutti gli agenti uno alla volta fino a quando non verrà risposta o va in timeout in attesa nella coda.
  > [!NOTE]
  > L'instradamento seriale ignorerà gli agenti che sono **Non in linea**, che hanno impostato la presenza su **Non disturbare**o hanno **Rinunciato** scegliendo di non ricevere chiamate da questa coda.
- **Round Robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata otterrà lo stesso numero di chiamate dalla coda. Questo potrebbe essere molto utile in un ambiente di vendita in entrata per assicurare pari opportunità tra tutti gli agenti di chiamata.

### <a name="select-an-agent-opt-out-option"></a>Selezionare un opzione di esclusione

![Screenshot delle opzioni di disattivazione dell'agente, con callout numerati](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

**Opzione esclusione agente** Puoi scegliere di consentire agli agenti di coda di chiamata di disattivare la risposta alle chiamate provenienti da una coda particolare selezionando **Opzione esclusione agente**.

L'abilitazione di questa opzione consente a tutti gli agenti in questa coda di avviare o interrompere la ricezione delle chiamate da questa coda di chiamata. Puoi revocare il privilegio di esclusione dell'agente in qualsiasi momento, deselezionando la casella di controllo, includendo nuovamente automaticamente tutti gli agenti a questa coda (impostazione predefinita per tutti gli agenti).

Per accedere all'opzione di esclusione, gli agenti possono eseguire le seguenti operazioni:

 1. Aprire **Opzioni** nel proprio client desktop di Skype for Business.
 2. Nella scheda **Inoltro chiamata** di chiamata, fare clic sul collegamento **Modifica impostazioni online**.
 3. Nella pagina Impostazioni utente, fare clic su **Coda chiamate** e quindi deselezionare le caselle di controllo per una o più code per cui desiderano consentire il modo esclusione.

    > [!NOTE]
    > Gli agenti che usano app o endpoint diversi da Skype for business desktop possono accedere all'opzione opt-out dal portale [https://aka.ms/cqsettings](https://aka.ms/cqsettings)delle impostazioni utente.

![Icona del numero 2, che fa riferimento a un callout nell'](media/sfbcallout2.png)
**impostazione di avviso dell'agente** screenshot precedente

In questo modo viene definita la durata di un agente notificato di una chiamata prima che i metodi di routing seriale o Round Robin vengano spostati nell'agente successivo.

L'impostazione predefinita è 30 secondi, ma può essere impostata per un massimo di 3 minuti.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Impostare le opzioni di gestione di overflow e timeout delle chiamate

![Screenshot delle opzioni di gestione dell'overflow, con callout numerati](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

**Chiamate massime in coda** Consente di impostare il numero massimo di chiamate che possono aspettare in coda contemporaneamente. Il valore predefinito è 50, ma può variare da 0 a 200. Quando viene raggiunto questo limite, la chiamata verrà gestita nel modo definito dall'impostazione **Quando viene raggiunto il numero massimo di chiamate**, di seguito.

* * *

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

**Quando viene raggiunto il numero massimo di chiamate** Quando la coda di chiamata raggiunge le dimensioni massime (impostate usando le **chiamate massime nell'impostazione della coda** ), è possibile scegliere cosa succede alle nuove chiamate in arrivo.

- **Disconnetti** La chiamata verrà disconnessa.
- **Reindirizza a** Quando si sceglie questo pulsante, selezionare una delle opzioni seguenti:

  - **Persona nella tua azienda** Un utente online con una licenza di **sistema telefonico** ed essere abilitato per VoIP aziendale o avere un piano per le chiamate. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. A questo scopo, seleziona una **persona nella tua azienda** e imposta questa persona affinché le chiamate vengano inoltrate direttamente alla segreteria telefonica.

  Per informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).

  - **Applicazione vocale** Selezionare il nome di una coda di chiamata o di un operatore automatico già creato.

* * *

![Icona del numero 3, che fa riferimento a un callout nella schermata precedente](media/sfbcallout3.png)

**Timeout chiamata: tempo massimo di attesa** Puoi anche decidere quanto tempo può rimanere in attesa di una chiamata nella coda prima che venga interrotto e debba essere reindirizzato o disconnesso. La destinazione è basata sull'impostazione **Quando una chiamata va in timeout**. Puoi impostare un tempo da 0 a 45 minuti.

Puoi impostare il valore di timeout in secondi, a intervalli di 15 secondi. In questo modo è possibile modificare il flusso delle chiamate con maggiore granularità. Ad esempio, puoi specificare che le chiamate non risposte da un agente entro 30 secondi passa a un operatore automatico di ricerca della directory.

![Icona del numero 4, che fa riferimento a un callout nella schermata precedente](media/sfbcallout4.png)

**Timeout chiamata** Quando la chiamata raggiunge il limite impostato sul periodo di **attesa di una chiamata nell'impostazione della coda** , è possibile scegliere cosa succede a questa chiamata:

- **Disconnetti** La chiamata verrà disconnessa.
- **Reindirizzare la chiamata a** Quando si sceglie questa opzione, saranno disponibili le opzioni seguenti:
  - **Persona nella tua azienda** Un utente online con una licenza di **sistema telefonico** ed essere abilitato per VoIP aziendale o per avere piani di chiamata. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. A questo scopo, seleziona una **persona nella tua azienda** e imposta questa persona affinché le chiamate vengano inoltrate direttamente alla segreteria telefonica.

  Per informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).

  - **Applicazione vocale** Selezionare il nome di una coda di chiamata o di un operatore automatico già creato.

## <a name="changing-a-users-caller-id-for-outbound-calls"></a>Modifica dell'ID chiamante di un utente per le chiamate in uscita

Puoi proteggere l'identità di un utente modificando l'ID chiamante per le chiamate in uscita in una coda di chiamata, un operatore automatico o un numero di servizio creando un criterio usando il cmdlet **New-CsCallingLineIdentity** .

Per farlo, eseguire quanto segue:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Quindi applica il criterio per l'utente utilizzando il cmdlet ** Grant-CallingLineIdentity.** Per farlo, eseguire quanto segue:
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Per altre informazioni su come modificare le impostazioni dell'ID chiamante nell'organizzazione [, vedere come si può usare l'ID chiamante nell'organizzazione](/microsoftteams/how-can-caller-id-be-used-in-your-organization).

## <a name="call-queue-cmdlets"></a>Cmdlet della coda di chiamata

Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata. Questi sono i cmdlet necessari per gestire una coda di chiamata.
  
- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Altre informazioni su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell è possibile gestire Office 365 e Microsoft teams usando un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft teams, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:

  - [Gestire Office 365 con Windows PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Configurare il computer per Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Argomenti correlati

[Ecco cosa offre il Sistema telefonico in Office 365](here-s-what-you-get-with-phone-system.md)

[Recupero di numeri di telefono del servizio](getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
