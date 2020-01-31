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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: Informazioni su come configurare il sistema telefonico per le code delle chiamate cloud con Microsoft teams.
ms.openlocfilehash: c33baabdce8366ed9a4027c0b1e030f54eef543b
ms.sourcegitcommit: 43a17ce6fea3951719b55bfbda03c500cef4816c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41620003"
---
# <a name="create-a-cloud-call-queue"></a>Creare una coda delle chiamate nel cloud

Le code delle chiamate cloud possono essere fornite:

- Messaggio di saluto.
- Musica mentre le persone sono in attesa.
- Reindirizzamento delle chiamate per chiamare gli agenti in liste di distribuzione via mail e gruppi di sicurezza.
- Impostazione di parametri diversi, ad esempio la dimensione massima della coda, il timeout e le opzioni di gestione delle chiamate.
- Segreteria telefonica condivisa per i chiamanti per l'uscita di un messaggio per un'organizzazione.

Non si associa direttamente un numero di telefono a una coda di chiamata, ma il numero di telefono è associato a un [account delle risorse](manage-resource-accounts.md). Una coda di chiamata può essere chiamata direttamente o accessibile tramite una selezione in un operatore automatico.

Il chiamante sente la musica mentre è in attesa e la chiamata si connette agli agenti di chiamata in ordine *First in, First out* (FIFO).

Tutte le chiamate nella coda vengono inviate agli agenti da uno dei metodi seguenti:

- Con il routing di Attendant, la prima chiamata nella coda squilla tutti gli agenti contemporaneamente.
- Con il routing seriale, la prima chiamata nella coda squilla tutti gli agenti di chiamata uno alla volta.
- Con Round Robin, il routing delle chiamate in arrivo è bilanciato in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda.

    > [!NOTE]
    > Gli agenti di chiamata **offline**, hanno impostato la loro presenza su non **disturbare** o hanno scelto di non ricevere chiamate nella coda di chiamata.

- Solo una notifica di chiamata in arrivo (per la chiamata a capo della coda) alla volta passa agli agenti di chiamata.
- Una volta che un agente di chiamata accetta la chiamata, la prossima chiamata in arrivo in coda viene segnalata agli agenti di chiamata.

> [!NOTE]
> Questo articolo si applica sia a Microsoft teams che a Skype for business online.

## <a name="step-1--get-started"></a>Passaggio 1: iniziare

Per iniziare a utilizzare le code di chiamata, è importante ricordare quanto segue.

- È necessaria una coda di chiamata per avere un account di risorse associato. Per informazioni dettagliate sugli account delle risorse, vedere [gestire gli account delle risorse in teams](manage-resource-accounts.md) .
- Quando si assegna un numero di telefono a un account delle risorse, è ora possibile usare la licenza per gli [utenti virtuali](teams-add-on-licensing/virtual-user.md)del sistema telefonico senza costi. Sistema telefonico consente di usare i numeri di telefono a livello di organizzazione per l'operatore automatico a basso costo e i servizi di Accodamento chiamate.

> [!NOTE]
> I numeri di servizio di routing diretto per le code di chiamata sono supportati solo per gli utenti e gli agenti di Microsoft teams.

> [!NOTE]
> Per reindirizzare le chiamate alle persone dell'organizzazione online, devono avere una licenza per il **sistema telefonico** e essere abilitate per VoIP aziendale o avere piani di chiamata di Office 365. Vedere [assegnare le licenze di Microsoft teams](assign-teams-licenses.md). Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell. Ad esempio, Esegui:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Per altre informazioni sui piani di chiamate di Office 365, vedere [sistemi di telefonia e](calling-plan-landing-page.md) piani di chiamata e [piani di chiamata per Office 365](calling-plans-for-office-365.md).

- È possibile assegnare solo i numeri di telefono a pedaggio e numero verde delle code di chiamate cloud disponibili nell'interfaccia di **amministrazione di Microsoft teams** o trasferiti da un altro provider di servizi. I crediti per le comunicazioni sono necessari per i numeri di servizio gratuiti.

    > [!NOTE]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati a code di chiamata, ma solo numeri di telefono di servizio a pagamento o numeri verdi.

- I client seguenti sono supportati per gli agenti di chiamata associati a una coda di chiamata cloud:

  - Client desktop Skype for business 2016 (versioni 32 e 64 bit)

  - Client desktop Lync 2013 (versioni 32 e 64 bit)

  - Tutti i modelli di telefono IP supportati per Microsoft teams. Vedere [ottenere telefoni per Skype for business online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).

  - Client Mac Skype for Business (versione 16.8.196 e versioni successive)

  - Client Android Skype for Business (versione 6.16.0.9 e versioni successive)

  - Client iPhone Skype for Business (versione 6.16.0 e versioni successive)

  - Client Mac Skype for Business (versione 6.16.0 e versioni successive)

  - Client Windows Microsoft Teams (versioni a 32 bit e 64 bit)

  - Client Microsoft Teams Mac

  - App per iPhone di Microsoft Teams

  - App Microsoft teams Android

    > [!NOTE]
    > Le code di chiamata assegnate a un numero di routing diretto non supportano i client di Skype for business, i client Lync o i telefoni IP Skype for business come agenti.

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a>Passaggio 2: ottenere o trasferire numeri di servizio a pagamento o a numero verde

Prima di poter creare e configurare le code di chiamata, è necessario ottenere o trasferire i numeri di servizio a pagamento o a pedaggio esistenti. Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono](getting-service-phone-numbers.md) o se si vuole trasferire un numero di servizio esistente, vedere trasferire i [numeri di telefono in Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md). Dopo aver ottenuto il pedaggio o i numeri di telefono del servizio gratuito, verranno visualizzati nei numeri di telefono della**segreteria** > **telefonica**dell'interfaccia di amministrazione > di **Microsoft teams**. I numeri verdi saranno elencati con un **tipo** di servizio numero **-gratuito**.

> [!NOTE]
> Se si è al di fuori degli Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft teams per ottenere i numeri di servizio. Vai a [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per vedere come farlo dall'esterno degli Stati Uniti.

Quando si configurano più operatori automatici, in genere si assegna un numero di telefono all'account delle risorse dell'operatore automatico principale. Gli account delle risorse associati agli operatori automatici annidati o alle code di chiamata spesso non hanno bisogno di numeri di telefono. L'operatore automatico può indirizzare i chiamanti alle code di chiamata o agli operatori automatici annidati anche se non hanno un numero di telefono. In questi casi, è possibile creare tutti gli operatori automatici e le code di chiamata nel sistema senza assegnare le opzioni del tastierino e quindi modificare le impostazioni in un secondo momento. Una coda di chiamata o un operatore automatico deve esistere per impostarla come opzione di menu.

## <a name="step-3--create-a-call-queue"></a>Passaggio 3: creare una coda di chiamata

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Ogni coda di chiamata è necessaria per avere un [account di risorse](manage-resource-accounts.md)associato. Devi prima creare l'account della risorsa, quindi puoi associarlo alla coda di chiamata.

### <a name="use-the-microsoft-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Microsoft Teams

Nell'interfaccia di **amministrazione di Microsoft teams**,**code di chiamata** **vocale** > , quindi fare clic su **+ Aggiungi nuovo**:

### <a name="set-the-display-name-and-resource-account"></a>Impostare il nome visualizzato e l'account delle risorse

![Screenshot di una nuova coda di chiamata, con callout numerati](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![Icona del numero 1, fa riferimento a un callout nel](media/sfbcallout1.png)
**nome** dello screenshot precedente immettere un nome visualizzato descrittivo per la coda di chiamata. Questo nome è obbligatorio e può contenere fino a 64 caratteri, inclusi gli spazi.

 Questo nome viene visualizzato nella notifica per la chiamata in arrivo.

* * *

![Icona del numero 2, fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

**Aggiungere account** Selezionare un account di risorse. Per avere un account delle risorse sono necessarie tutte le code di chiamata. Gli account delle risorse non sono obbligatori per avere un numero di telefono a pagamento o senza pedaggio.

Se non sono presenti elenchi, ottenere i numeri di servizio e assegnarli a un account di risorse prima di creare la coda di chiamata, come descritto in precedenza. Per ottenere i numeri di servizio, vedere [ottenere i numeri di telefono del servizio](getting-service-phone-numbers.md). Vedere [gestire gli account delle risorse in teams](manage-resource-accounts.md) per informazioni specifiche su come assegnare un numero di telefono.

> [!NOTE]
> Se si vuole o è necessario assegnare un **dominio** , assegnarlo all'account delle risorse per la coda di chiamata.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Impostare il saluto e la musica durante l'attesa

![screenshot delle opzioni di saluto e musica, con callout numerati](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![Icona del numero 1, fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

**Saluto** il messaggio di saluto facoltativo riprodotto per le persone che chiamano il numero della coda di chiamata.

È possibile caricare un file audio (formati. wav,. mp3 o. WMA).

![Icona del numero 2, fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

**Musica in attesa** È possibile usare la musica predefinita in attesa fornita con la coda di chiamata. È anche possibile caricare un file audio in formato WAV, MP3 o WMA da usare come musica personalizzata in attesa.

* * *

### <a name="select-the-call-answering-options"></a>Selezionare le opzioni di segreteria telefonica

![Screenshot delle opzioni di segreteria telefonica](media/5d249515-d532-4af2-90da-011404028b89.png) 

![Icona del numero 1, fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

Per aggiungere direttamente singoli agenti, senza aggiungerli a un gruppo, fare clic su **Aggiungi utenti**. Inserire singoli agenti nell'ordine in cui si vuole che ricevano la chiamata. È possibile aggiungere fino a 20 singoli agenti (per aggiungere più di 20, inserirli in un gruppo).

Le chiamate vengono instradate prima a singoli agenti, quindi agli agenti in gruppi. 

È possibile selezionare fino a 200 gli agenti di chiamata che appartengono a una delle seguenti liste di distribuzione o gruppi:

- Gruppo Office 365
- Gruppo di sicurezza
- Elenco di distribuzione

Gli agenti di chiamata selezionati devono essere: 

- Utenti online con licenza di sistema telefonico e VoIP aziendale abilitato 
- Utenti online con un piano per le chiamate
- Utenti di Skype for Business Server locale

  > [!NOTE]
  > Questo vale anche se vuoi reindirizzare le chiamate agli utenti dell'organizzazione online. Questi utenti devono avere una licenza per il **sistema telefonico** e VoIP aziendale abilitato **o** avere un piano di chiamata. Per altre informazioni, vedere [assegnare licenze Skype for business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [assegnare licenze Microsoft teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)o [quale piano per le chiamate è giusto per l'utente?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)

 Per abilitare un agente per VoIP aziendale, è possibile usare Windows PowerShell. Ad esempio, Esegui:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Utenti con una licenza di **sistema telefonico** o un piano di chiamata aggiunto a un gruppo di Office 365; una lista di distribuzione abilitata per la posta elettronica; o un gruppo di sicurezza. Quando si aggiunge un agente in una lista di distribuzione o un gruppo di sicurezza come agente della coda di chiamata, è possibile che la prima chiamata arrivi fino a tre ore. Una lista di distribuzione o un gruppo di sicurezza appena creato può richiedere fino a 48 ore per diventare disponibile per l'uso con le code di chiamata. I Gruppi di Office 365 appena creati sono disponibili quasi immediatamente.

- Se gli agenti usano l'app Microsoft teams per le chiamate alla coda di chiamata, devono essere in modalità TeamsOnly.

![Screenshot del riquadro Aggiungi agenti chiamata](media/skype-for-business-add-agents-to-call-queue.png)

![Icona del numero 2, fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

**Metodo di routing** È possibile scegliere **Supervisore**, **seriale**o **Round Robin** come metodo di distribuzione. Tutte le code di chiamata nuove ed esistenti hanno il routing di Attendant selezionato per impostazione predefinita. Quando viene usato il routing di Attendant, la prima chiamata nella coda squilla tutti gli agenti di chiamata contemporaneamente. Il primo agente di chiamata a prendere la chiamata riceve la chiamata.

- Il **routing degli assistenti** fa sì che la prima chiamata nella coda squilli tutti gli agenti di chiamata contemporaneamente. Il primo agente di chiamata a prendere la chiamata riceve la chiamata.
- **Routing seriale** le chiamate in arrivo squillano tutti gli agenti di chiamata uno alla volta, dall'inizio dell'elenco agente chiamate. Non è possibile ordinare gli agenti nell'elenco agente chiamate. Se un agente respinge o non prende una chiamata, la chiamata suonerà l'agente successivo e proverà tutti gli agenti finché non viene prelevato o non viene ritirato.
  > [!NOTE]
  > Con il routing seriale, per gli agenti **offline** o che hanno impostato la loro presenza su **non disturbare**, la chiamata verrà instradata a tali utenti e non riesce a connettere l'utente non disponibile, il routing all'agente successivo nell'elenco degli agenti. Questo non è il caso se l'agente ha **scelto** di ricevere chiamate dalla coda di chiamata. Per ridurre l'intervallo di tempo che la chiamata instrada all'agente successivo in linea, il tempo di avviso dell'agente può essere ridotto.
- **Round Robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda. Questo potrebbe essere auspicabile in un ambiente di vendita in entrata per assicurare la parità di opportunità tra tutti gli agenti di chiamata.

### <a name="select-an-agent-opt-out-option"></a>Selezionare un'opzione di opt-out per l'agente

![Screenshot delle opzioni di opt-out per gli agenti, con callout numerati](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![Icona del numero 1, fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

**L'agente può rifiutare di ricevere chiamate** È possibile scegliere di consentire agli agenti della coda di chiamata di rifiutare l'annullamento delle chiamate da una coda specifica abilitando questa opzione.

L'abilitazione di questa opzione consente a tutti gli agenti in questa coda di avviare o interrompere la ricezione delle chiamate da questa coda di chiamata. Puoi revocare il privilegio di esclusione dell'agente in qualsiasi momento, deselezionando la casella di controllo, includendo nuovamente automaticamente tutti gli agenti a questa coda (impostazione predefinita per tutti gli agenti).

Per accedere all'opzione opt-out, gli agenti possono:

 1. Aprire **Opzioni** nel proprio client desktop di Skype for Business.
 2. Nella scheda **Inoltro chiamata** di chiamata, fare clic sul collegamento **Modifica impostazioni online**.
 3. Nella pagina impostazioni utente fare clic su **code di chiamata**e quindi deselezionare le caselle di controllo per escludere le code.

    > [!NOTE]
    > Gli agenti che usano app o endpoint diversi da Skype for business desktop possono accedere all'opzione opt-out dal portale [https://aka.ms/cqsettings](https://aka.ms/cqsettings)delle impostazioni utente.
    >
    > Se gli agenti si trovano nei client desktop di Microsoft teams, possono rifiutare l'opt-out usando le impostazioni di chiamata. 

![Icona del numero 2, fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

**Impostazione avviso agente**

In questo modo viene definita la durata di un agente notificato di una chiamata prima che i metodi di routing seriale o Round Robin vengano spostati nell'agente successivo.

L'impostazione predefinita è 30 secondi, ma può essere impostata per un massimo di 3 minuti.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Impostare le opzioni di gestione di overflow e timeout delle chiamate

![Screenshot delle opzioni di gestione dell'overflow, con callout numerati](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Icona del numero 1, fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

**Chiamate massime in coda** Consente di impostare il numero massimo di chiamate che possono aspettare in coda contemporaneamente. Il valore predefinito è 50, ma può variare da 0 a 200. Quando viene raggiunto questo limite, la chiamata viene gestita nel modo in cui viene impostata la posizione in **cui viene raggiunto il numero massimo di chiamate** .

* * *

![Icona del numero 2, fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

**Quando viene raggiunto il numero massimo di chiamate** Quando la coda di chiamata raggiunge le dimensioni massime (impostate usando le **chiamate massime nell'impostazione della coda** ), è possibile scegliere cosa succede alle nuove chiamate in arrivo.

- **Disconnetti** La chiamata è disconnessa.
- **Reindirizza a** Quando si sceglie questo pulsante, selezionare una delle opzioni seguenti:

  - **Persona nella tua azienda** Un utente online con una licenza di **sistema telefonico** ed essere abilitato per VoIP aziendale o avere un piano per le chiamate. È possibile configurarlo in modo che il chiamante possa essere inviato alla segreteria telefonica. A questo scopo, seleziona una **persona nella tua azienda** e imposta questa persona affinché le chiamate vengano inoltrate direttamente alla segreteria telefonica.

  Per informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).

  - **Applicazione vocale** Selezionare il nome di un account di risorsa associato a una coda di chiamata o a un operatore automatico già creato.

* * *

![Icona del numero 3, fa riferimento a un callout nella schermata precedente](media/sfbcallout3.png)

**Timeout chiamata: tempo massimo di attesa** Puoi anche decidere quanto tempo può rimanere in attesa di una chiamata nella coda prima che venga interrotto e debba essere reindirizzato o disconnesso. Il punto in cui viene reindirizzato si basa su come impostare l'impostazione quando viene impostato il timeout **di una chiamata** . Puoi impostare un tempo da 0 a 45 minuti.

Puoi impostare il valore di timeout in secondi, a intervalli di 15 secondi. In questo modo è possibile modificare il flusso delle chiamate con maggiore granularità. Ad esempio, puoi specificare che le chiamate non risposte da un agente entro 30 secondi passa a un operatore automatico di ricerca della directory.

![Icona del numero 4, fa riferimento a un callout nella schermata precedente](media/sfbcallout4.png)

**Timeout chiamata** Quando la chiamata raggiunge il limite impostato sul periodo di **attesa di una chiamata nell'** impostazione della coda, è possibile scegliere cosa succede alla chiamata:

- **Disconnetti** La chiamata è disconnessa.
- **Reindirizzare la chiamata a** Quando si sceglie questa opzione, sono disponibili le opzioni seguenti:
  - **Persona nella tua azienda** Un utente online con una licenza di **sistema telefonico** ed essere abilitato per VoIP aziendale o per avere piani di chiamata. Per configurarlo in modo che la persona che chiama può essere inviata alla segreteria telefonica, selezionare una **persona nella società** e impostare questa persona per inoltrare le chiamate direttamente alla segreteria telefonica.

  Per informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).

  - **App vocale** Selezionare il nome di un account di risorsa associato a una coda di chiamata o a un operatore automatico già creato.

## <a name="change-caller-id-for-outbound-calls"></a>Modificare l'ID chiamante per le chiamate in uscita

Per proteggere l'identità di un agente di chiamata, modificare l'ID chiamante per le chiamate in uscita in una coda di chiamata, un operatore automatico o un numero di servizio con il cmdlet **New-CsCallingLineIdentity** , come illustrato nell'esempio seguente:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Applicare quindi il criterio all'utente con il cmdlet **Grant-CallingLineIdentity** , come illustrato nell'esempio seguente: 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Per altre informazioni, vedere [come può essere usato l'ID chiamante nell'organizzazione](/microsoftteams/how-can-caller-id-be-used-in-your-organization).

## <a name="call-queue-cmdlets"></a>Cmdlet della coda di chiamata

Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata. Ecco i cmdlet usati per gestire una coda di chiamata.

- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Altre informazioni su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell è possibile gestire Office 365 e Microsoft teams con un unico punto di amministrazione. Può semplificare il lavoro quotidiano, quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell offre numerosi vantaggi in velocità, semplicità e produttività nell'interfaccia di amministrazione di Microsoft teams quando si apportano modifiche per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:

  - [Gestire Office 365 con Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Argomenti correlati

[Ecco cosa offre il Sistema telefonico in Office 365](here-s-what-you-get-with-phone-system.md)

[Recuperare numeri di telefono del servizio](getting-service-phone-numbers.md).

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
