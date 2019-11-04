---
title: Gestire l'accesso esterno (Federazione) in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.externalaccess.overview
description: I team o l'amministratore IT può configurare l'accesso esterno per altri domini (Federazione) per consentire agli utenti di tali domini di partecipare a teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: e6eb1cab6503c443d3fb312769f9f1e0255c294a
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925047"
---
<a name="manage-external-access-in-microsoft-teams"></a>Gestire l'accesso esterno in Microsoft Teams
======================================================

L'accesso esterno è un modo per gli utenti di team esterni provenienti da un intero dominio per trovare, chiamare, chattare e configurare riunioni con l'utente in teams. È anche possibile usare l'accesso esterno per comunicare con utenti esterni che usano ancora Skype for business (online e locale) e Skype (in arrivo all'inizio di 2020).

Se si vuole consentire agli utenti esterni di accedere a team e canali, l’accesso guest potrebbe essere un’opzione migliore. Per altre informazioni sulle differenze tra l'accesso esterno e l'accesso guest, vedere [confrontare l'accesso esterno e Guest](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Usare l'accesso esterno quando:
  
- Si hanno utenti in domini diversi che devono collaborare. Ad esempio, Rob@contoso.com e Ann@northwindtraders.com stanno lavorando a un progetto insieme ad altri nei domini contoso.com e northwindtraders.com.

- Si vuole che gli utenti dell'organizzazione usino i team per contattare persone di aziende specifiche all'esterno dell'organizzazione.

- Si vuole che chiunque altro al mondo usi i team per poter trovare e contattare l'utente, usando l'indirizzo di posta elettronica. 




> [!IMPORTANT]
> Attualmente, per federare all'interno dell'app Microsoft Teams a un utente esterno all'esterno dell'organizzazione che non è attualmente Guest di Azure Active Directory (Azure AD) o tenant, è necessario essere configurati correttamente per Hybrid e spostati in Skype for business online. A partire dal 25 febbraio 2019, teams non supporta la Federazione nativa senza che l'utente del profilo SIP venga ospitato in Skype for business online. Per altre informazioni su come configurare l'account per Hybrid e quindi passare a teams, vedere [aggiornare la distribuzione ibrida di Skype for business ai team](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).






## <a name="plan-for-external-access"></a>Pianificare l'accesso esterno

Per impostazione predefinita, l'accesso esterno è attivato in teams, il che significa che l'organizzazione può comunicare con tutti i domini esterni. Se si aggiungono domini bloccati, tutti gli altri domini saranno consentiti; Se si aggiungono domini consentiti, tutti gli altri domini verranno bloccati. Esistono tre scenari per configurare l'accesso esterno nell'interfaccia di amministrazione di Teams (**accesso esterno alle****Impostazioni** > a livello di organizzazione):

- **Open Federation**: questa è l'impostazione predefinita in teams e consente alle persone dell'organizzazione di trovare, chiamare, chattare e configurare riunioni con persone esterne all'organizzazione in qualsiasi dominio.

    In questo scenario, gli utenti possono comunicare con tutti i domini esterni che gestiscono team o Skype for business e usano la Federazione aperta o hanno aggiunto il dominio all'elenco Consenti.

- **Consenti domini specifici**: se si aggiungono domini a un elenco **Consenti** , si limita l'accesso esterno solo ai domini consentiti. Dopo aver configurato un elenco di domini consentiti, tutti gli altri domini verranno bloccati. Per consentire domini specifici, fare clic su **Aggiungi un dominio**, aggiungere il nome di dominio, fare clic **su azione per eseguire il dominio**e quindi selezionare **consentito**.

- **Bloccare domini specifici** : se si aggiungono domini a un elenco di **blocchi** , è possibile comunicare con tutti i domini esterni *tranne* quelli bloccati. Per bloccare specifici domini, fare clic su **Aggiungi un dominio**, aggiungere il nome di dominio, fare clic **su azione per eseguire il dominio**e quindi selezionare **bloccato**. Dopo aver configurato un elenco di domini bloccati, saranno consentiti tutti gli altri domini.

## <a name="allow-or-block-domains"></a>Consentire o bloccare i domini

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>Passaggio 1-consentire all'organizzazione di comunicare con un'altra organizzazione di Teams

![Icona che mostra il logo](media/teams-logo-30x30.png)di Microsoft teams**con l'interfaccia di amministrazione di Microsoft teams**  

1. Nella barra di spostamento sinistra passa a **Impostazioni** > a livello di organizzazione per**l'accesso esterno**.

2. Attiva/disattiva gli **utenti possono comunicare con Skype for business e gli utenti di teams** **si attivano.**

     ![Schermata del pulsante di accesso esterno attivato](media/manage-external-access-2.png).

3. Se si vuole consentire a tutte le organizzazioni dei team di comunicare con gli utenti dell'organizzazione, passare al passaggio 5.

4. Se si vogliono limitare le organizzazioni che possono comunicare con gli utenti dell'organizzazione, è possibile consentire l'accesso a tutti tranne alcuni domini oppure consentire solo domini specifici. 

    - Per consentire a tutti eccetto alcuni domini, aggiungere i domini che si desidera bloccare facendo clic su **Aggiungi dominio**. Nel riquadro **Aggiungi un dominio** Digitare il nome del dominio, fare clic su **bloccato**e quindi fare clic su **fine**. 
    - Per limitare le comunicazioni a specifiche organizzazioni, aggiungere tali domini all'elenco con lo stato **consentito**. Dopo aver aggiunto un dominio all'elenco Consenti, le comunicazioni con altre organizzazioni saranno limitate solo alle organizzazioni i cui domini si trovano nell'elenco Consenti. 

5. Fai clic su **Salva**.

6. Verificare che l'amministratore dell'organizzazione di altri team completi gli stessi passaggi. Nell'elenco dei **domini consentiti** , ad esempio, l'amministratore deve immettere il dominio per l'azienda se limita le organizzazioni che possono comunicare con gli utenti.

### <a name="step-2---test-it"></a>Passaggio 2: testarlo

Per testare la configurazione, è necessario un utente di teams che non si trova dietro il firewall.
  
1. Dopo che l'amministratore dell'organizzazione ha modificato le impostazioni di **accesso esterno** , è consigliabile andare bene.

2. Nell'app teams cercare l'indirizzo di posta elettronica di una persona e inviare una richiesta di chat.

3. Chiedere al contatto del team di inviare una richiesta di chat. Se non si riceve la richiesta, il problema è che le impostazioni del firewall (presumendo che abbiano già confermato le impostazioni del firewall siano corrette).

4. Un altro modo per verificare se il problema è il firewall consiste nell'accedere a una posizione Wi-Fi non dietro il firewall. ad esempio un coffee shop e usare teams per inviare una richiesta al contatto per la chat. Se il messaggio passa attraverso la posizione Wi-Fi, ma non quando si è al lavoro, si sa che il problema è il firewall.

> [!NOTE]
> Se si e un altro utente attiva l'accesso esterno e si concedono i domini di un altro, questo funzionerà. Se non funziona, l'altro utente deve assicurarsi che la configurazione non blocchi il dominio.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Comunicare con gli utenti in un'organizzazione di Skype for business online

Se si sta configurando l'accesso esterno per consentire agli utenti del team di trovare e contattare gli utenti in un'organizzazione Skype for business che limita chi può contattare gli utenti, seguire i passaggi per configurare l'accesso esterno dal dominio al dominio dell'altra organizzazione. Chiedi quindi all'amministratore dell'altra organizzazione di seguire i passaggi seguenti per configurare l'accesso esterno per Skype for business online. 

Per informazioni specifiche sugli scenari comuni di Skype for business online, vedere [scenari di accesso esterno comuni](#common-external-access-scenarios) .

![Icona che mostra il logo](media/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**

Fare in modo che l'amministratore dell'organizzazione faccia questa procedura:

1. Nell'interfaccia di amministrazione di Microsoft 365 accedere a **** > **Teams** > di interfaccia di amministrazione &**portale legacy**Skype.
  
2. Nell'interfaccia di **amministrazione di Skype for business**scegli **** > **comunicazioni esterne**dell'organizzazione.

3. Per configurare la comunicazione con un'azienda specifica o con utenti di un altro dominio, nella casella a discesa scegliere **solo per i domini consentiti**.

    In alternativa, se si vuole consentire la comunicazione con tutti gli altri utenti del mondo che hanno aperto i criteri di Skype for business, scegliere attivato **eccetto i domini bloccati**. Questa è l'impostazione predefinita.

4. In **domini bloccati o consentiti**scegliere **+** e quindi aggiungere il nome del dominio che si vuole consentire.

## <a name="common-external-access-scenarios"></a>Scenari di accesso esterno comuni

|**Se vuoi...**  |**Operazione da eseguire**  |
|---------|-----------------------|
|Consentire **agli utenti del team** dell'organizzazione di comunicare con **gli utenti di Team** in un'altra organizzazione (esterna).|In accesso esterno aggiungere il dominio esterno all'elenco consentiti o usare la Federazione aperta. Fare in modo che l'amministratore dell'organizzazione di altri team faccia la stessa cosa.      |
|Consentire **agli utenti del team** dell'organizzazione di comunicare con **gli utenti di Skype for business online** nella stessa organizzazione.  |Abilitare la modalità di coesistenza o scegliere la modalità di aggiornamento delle isole per supportare gli utenti di Skype for business nell'organizzazione.   |
|Consentire **agli utenti del team** dell'organizzazione di comunicare con **gli utenti di Skype for business online** in un'altra organizzazione (esterna).      |In accesso esterno aggiungere il dominio esterno all'elenco consentiti o usare la Federazione aperta. <br><br>Attivare **gli utenti possono comunicare con l'impostazione utenti Skype for business e teams** in Access esterno. Fare in modo che l'amministratore dell'organizzazione di altri team faccia la stessa cosa. <br><br>**Nota**: il dominio esterno con gli utenti di Skype for business deve abilitare la modalità di coesistenza o scegliere la modalità di aggiornamento delle isole per supportare gli utenti di Skype for business nell'organizzazione.|
|Consentire **agli utenti del team** dell'organizzazione di comunicare con utenti **Skype** dall'interno o dall'esterno dell'organizzazione.   | Questo scenario sarà disponibile a breve. <br><br>**Importante**: gli utenti del team non sono ancora in grado di comunicare con gli utenti Skype, ma gli utenti di Skype for business possono continuare a comunicare con utenti Skype all'interno o all'esterno dell'organizzazione. Attivare gli utenti **possono comunicare con Skype for business e** gli utenti di teams e **gli utenti di Skype for business possono comunicare con le impostazioni degli utenti Skype** in Access esterno. |
|Consentire **agli utenti di Skype for business online** di comunicare con **gli utenti di Team** in un'altra organizzazione di Office 365.| Gli utenti di Skype for business online possono comunicare con gli utenti di team in un'altra organizzazione se gli utenti si trovano in una delle seguenti modalità di aggiornamento: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; e gli utenti del team dell'altra organizzazione sono in modalità TeamsOnly. <br><br>Attivare gli **utenti possono comunicare con l'impostazione utenti Skype for business e teams** in Access esterno. Quindi, l'amministratore dell'organizzazione di altri team esegue le stesse operazioni.|
|Consentire agli **utenti di Skype for business online** di comunicare con **gli utenti di Skype for business online** da un'altra organizzazione di Office 365.    | Gli utenti di Skype for business online possono comunicare con gli utenti di Skype for business online in un'altra organizzazione se gli utenti si trovano in una delle seguenti modalità di aggiornamento: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; e gli utenti di Skype for business online dell'altra organizzazione si trovano in una delle seguenti modalità di aggiornamento: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Attivare gli **utenti possono comunicare con l'impostazione utenti Skype for business e teams** in Access esterno. Quindi, l'amministratore dell'organizzazione di altri team esegue le stesse operazioni.|
|Consentire **agli utenti di Skype for business online** di comunicare con **utenti Skype for business** da un'organizzazione locale.     |Gli utenti di Skype for business online possono comunicare con utenti Skype for business da un'organizzazione locale se gli utenti si trovano in una delle seguenti modalità di aggiornamento: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; e gli utenti di Skype for business online dell'altra organizzazione si trovano in una delle seguenti modalità di aggiornamento: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Attivare gli **utenti possono comunicare con l'impostazione utenti Skype for business e teams** in Access esterno. Quindi, l'amministratore dell'organizzazione di altri team esegue le stesse operazioni.|
|Consentire **agli utenti di Skype for business online** di comunicare con **utenti Skype** (all'interno o all'esterno dell'organizzazione).   |Attivare gli **utenti di Skype for business in grado di comunicare con l'impostazione utenti Skype** in Access esterno.|

> [!IMPORTANT]
> Non è necessario aggiungere **domini Skype** come domini consentiti per consentire ai team o agli utenti di Skype for business online di comunicare con utenti Skype all'interno o all'esterno dell'organizzazione. Tutti i **domini Skype** sono in whitelist, quindi tutti i domini sono considerati consentiti.



## <a name="how-does-external-access-compare-with-guest-access"></a>Come viene confrontato l'accesso esterno con l'accesso Guest?

Per informazioni sulla differenza tra l'accesso esterno e l'accesso guest, leggere [comunicare con gli utenti di altre organizzazioni](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Argomenti correlati

[Esperienza di chat nativa per utenti esterni (federati)](native-chat-for-external-users.md)
