---
title: Gestire l'accesso esterno (federazione)
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: L'amministratore IT o di Teams può configurare l'accesso esterno per altri domini (federazione), per consentire agli utenti di tali domini di trovare, chiamare, chattare e configurare riunioni con gli utenti della propria organizzazione.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 5a52e479b7dd813af786c33e494675fe7b8e9743
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766609"
---
# <a name="manage-external-access-in-microsoft-teams"></a>Gestire l'accesso esterno in Microsoft Teams

L'accesso esterno consente agli utenti di Teams esterni all'organizzazione di trovare, chiamare, chattare e configurare riunioni con la propria organizzazione in Teams. Si può usare l'accesso esterno anche per comunicare con utenti di altre organizzazioni che usano ancora Skype for Business (online o locale) e Skype (in anteprima).

Per consentire agli utenti di altre organizzazioni di accedere ai team e ai canali dell’organizzazione, è possibile usare l'accesso guest. Per altre informazioni sulle differenze tra accesso esterno e accesso guest, vedere [Confrontare l'accesso esterno e guest](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Usare l'accesso esterno quando:
  
- Utenti in domini esterni che devono collaborare. Ad esempio, Rob@contoso.com e Ann@northwindtraders.com lavorano a un progetto con altri nei domini contoso.com e northwindtraders.com.

- Si vuole che gli utenti dell'organizzazione usino Teams per contattare persone in specifiche aziende esterne all'organizzazione.

- Si vuole poter essere trovati e contattati da qualsiasi altro utente di Teams al mondo tramite il proprio indirizzo di posta elettronica. 

## <a name="plan-for-external-access"></a>Pianificare l'accesso esterno

L'accesso esterno è attivato per impostazione predefinita in Teams, quindi l'organizzazione può comunicare con tutti i domini esterni. Se si aggiungono domini bloccati, verranno consentiti tutti gli altri domini. Se si aggiungono domini consentiti, tutti gli altri domini verranno bloccati. L'eccezione a questa regola è se alle riunioni sono consentiti partecipanti anonimi. Esistono tre scenari per la configurazione dell'accesso esterno nell'interfaccia di amministrazione di Teams (**Utenti** > **Accesso esterno**):

> [!NOTE]
> Gli utenti Teams possono aggiungere app quando tengono riunioni o chat con persone di altre organizzazioni. Possono inoltre usare app condivise da componenti di altre organizzazioni quando prendono parte a riunioni o chat tenute da quelle organizzazioni. Si applicano i criteri sui dati dell’organizzazione dell’utente ospitante, così come le pratiche di condivisione dei dati di tutte le app di terze parti condivise da quell’organizzazione.

> [!NOTE]
> Se si disattiva l'accesso esterno nell'organizzazione, gli utenti esterni possono comunque partecipare alle riunioni mediante la partecipazione anonima. Per altre informazioni, vedere [Gestire le impostazioni di riunione in Teams](meeting-settings-in-teams.md).

- **Consenti tutti i domini esterni**: questa è l'impostazione predefinita in Teams e consente agli utenti dell'organizzazione di trovare, chiamare, chattare e configurare riunioni con persone esterne all'organizzazione in qualsiasi dominio.

    In questo scenario, gli utenti possono comunicare con tutti i domini esterni che eseguono Teams o Skype for Business, o che consentono tutti i domini esterni o che hanno aggiunto il dominio all'elenco dei domini consentiti.

- **Consentirei solo domini esterni specifici**: aggiungendo domini a un elenco **Consenti**, si limita l'accesso esterno ai soli domini consentiti. Dopo aver configurato un elenco di domini consentiti, tutti gli altri domini verranno bloccati. Per consentire domini specifici, fare clic su **Aggiungi un dominio**, aggiungere il nome di dominio, fare clic su **Azione da eseguire sul dominio** e quindi selezionare **Consentito**.

- **Bloccare domini specifici**: l'aggiunta di domini a un elenco di **blocco** è possibile comunicare con tutti i domini esterni *tranne* quelli bloccati. Per bloccare domini specifici, fare clic su **Aggiungi un dominio**, aggiungere il nome di dominio, fare clic su **Azione da eseguire sul dominio** e quindi selezionare **Bloccato**. Dopo aver configurato un elenco di domini bloccati, tutti gli altri domini verranno consentiti.

- **Bloccare tutti i domini esterni:** impedisce agli utenti dell'organizzazione di trovare, chiamare, chattare e configurare riunioni con persone esterne all'organizzazione in qualsiasi dominio.

> [!NOTE]
> I domini consentiti o bloccati si applicano alle riunioni solo se l'accesso anonimo alle riunioni è disattivato.

## <a name="allow-or-block-domains"></a>Consentire o bloccare domini

  **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

Consentire domini specifici

1. Nell'interfaccia di amministrazione di Teams, passare a **Utenti** > **Accesso esterno**.

2. In **Scegli i domini a cui hanno accesso gli utenti**, scegliere **Consenti solo domini esterni specifici.**

3. Selezionare **Consenti domini**.

4. Nella casella **Dominio** digitare il dominio che si desidera consentire e quindi fare clic su **Fatto.**

5. Se si desidera consentire un altro dominio, fare clic su **Aggiungi dominio.**

6. Fare clic su **Salva**.

Bloccare domini specifici

1. Nell'interfaccia di amministrazione di Teams, passare a **Utenti** > **Accesso esterno**.

2. In **Scegli i domini a cui gli utenti hanno accesso**, Scegli **Blocca solo domini esterni specifici**.

3. Selezionare **Blocca domini**.

4. Nella casella **Dominio** digitare il dominio che si desidera consentire e quindi fare clic su **Fatto.**

5. Se si desidera bloccare un altro dominio, fare clic su **Aggiungi un dominio**.

6. Fare clic su **Salva**.

Assicurarsi che l'amministratore dell'altra organizzazione di Teams completi questi stessi passaggi. Ad esempio, nell'elenco **domini consentiti**, l'amministratore deve immettere il dominio per l'azienda se limita le organizzazioni che possono comunicare con gli utenti della sua organizzazione.

## <a name="communicate-with-skype-users-preview"></a>Comunicare con gli utenti di Skype (anteprima)

Seguire questa procedura per consentire agli utenti di Teams nell'organizzazione di comunicare con gli utenti Skype e di chiamarli. Gli utenti di Teams potranno cercare utenti di Skype e avviare una conversazione a due di solo testo oppure una chiamata audio/video e viceversa.

  **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

1. Nel riquadro di spostamento sinistro passare a **Utenti** > **Accesso esterno**.

2. Abilita **Consenti agli utenti dell'organizzazione di comunicare con gli utenti di Skype** impostazione.

Per altre informazioni sui modi in cui gli utenti di Teams e gli utenti di Skype possono comunicare, incluse le limitazioni applicabili, vedere [Interoperabilità tra Teams e Skype](teams-skype-interop.md).

## <a name="block-unsolicited-contact-with-external-unmanaged-teams-users"></a>Bloccare i contatti non richiesti con gli utenti di Teams esterni non gestiti

Seguire questa procedura per impedire agli utenti di Teams dell'organizzazione di avere contatti non richiesti con utenti di Teams esterni i cui account non sono gestiti da un'organizzazione.

  **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

1. Nel riquadro di spostamento sinistro passare a **Utenti** > **Accesso esterno**.

2. Eseguire una di queste operazioni:

    - Per impedire agli utenti di Teams dell'organizzazione di comunicare con utenti Teams esterni i cui account non sono gestiti da un'organizzazione, disattivare l'impostazione **Le persone dell'organizzazione possono comunicare con gli utenti di Teams i cui account non sono gestiti da un'organizzazione** e deselezionare la casella di controllo **Gli utenti esterni con account Teams non gestiti da un'organizzazione possono contattare gli utenti dell'organizzazione**.

    - Per consentire agli utenti di Teams dell'organizzazione di comunicare con utenti di Teams esterni i cui account non sono gestiti da un'organizzazione se gli utenti di Teams hanno avviato il contatto, attivare l'impostazione **Le persone dell'organizzazione possono comunicare con gli utenti di Teams i cui account non sono gestiti da un'organizzazione** e deselezionare la casella di controllo **Gli utenti esterni con account Teams non gestiti da un'organizzazione possono contattare gli utenti dell'organizzazione**.

    - Per consentire agli utenti di Teams dell'organizzazione di comunicare con utenti di Teams esterni i cui account non sono gestiti da un'organizzazione e di ricevere richieste di comunicazione con tali utenti di Teams esterni, attivare l'impostazione **Le persone dell'organizzazione possono comunicare con gli utenti di Teams i cui account non sono gestiti da un'organizzazione** e selezionare la casella di controllo **Gli utenti esterni con account Teams non gestiti da un'organizzazione possono contattare gli utenti dell'organizzazione**.

## <a name="test-access"></a>Testare l'accesso

Per testare la configurazione è necessario un utente di Teams che non si trova dietro il proprio firewall aziendale.
  
1. Una volta configurate le impostazioni di **Accesso esterno** in entrambe le organizzazioni, si può procedere.

2. Nell'app Teams cercare l'utente per indirizzo di posta elettronica e inviare una richiesta di chat.

3. Chiedere al contatto di Teams di inviare una richiesta di chat. Se non si riceve la richiesta, il problema sono le impostazioni del firewall, supponendo di aver già verificato che le impostazioni firewall dell'altra organizzazione siano corrette.

4. Un altro modo per verificare se il problema è il firewall consiste nel recarsi in una posizione Wi-Fi non dietro il firewall, ad esempio una caffetteria, e usare Teams per inviare una richiesta di chat al contatto. Se il messaggio viene recapitato nella posizione Wi-Fi, ma non in ufficio, il problema è sicuramente il firewall aziendale.

> [!NOTE]
> Se due organizzazioni attivano l'accesso esterno e consentono i rispettivi domini, tutto funzionerà. In caso contrario, occorre verificare che una delle due configurazioni non stia bloccando l'altro dominio.

## <a name="limit-external-access-to-specific-people"></a>Limitare l'accesso esterno a utenti specifici

Se hai abilitato **Le persone della mia organizzazione possono comunicare con gli utenti di Teams i cui account non sono gestiti da un'organizzazione**, puoi limitare l'accesso esterno a persone specifiche utilizzando PowerShell.

È possibile usare lo script seguente, sostituendo *NomeCriterio* con il nome che si vuole assegnare al criterio e *NomeUtente* per ogni utente a cui si vuole poter usare l'accesso esterno.

Assicurarsi di aver installato il modulo [Microsoft Teams PowerShell prima](/microsoftteams/teams-powershell-install) di eseguire lo script.

```PowerShell
Connect-MicrosoftTeams

# Disable external access globally
Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false

# Create a new external access policy
New-CsExternalAccessPolicy -Identity <PolicyName> -EnableTeamsConsumerAccess $true

# Assign users to the policy
$users_ids = @("<UserName1>", "<UserName2>")
New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "<PolicyName>" -Identity $users_ids

```

Ad esempio:

```PowerShell
Connect-MicrosoftTeams

Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false

New-CsExternalAccessPolicy -Identity ContosoExternalAccess -EnableTeamsConsumerAccess $true

$users_ids = @("MeganB@contoso.com", "AlexW@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "ContosoExternalAccess" -Identity $users_ids

```

Per altri esempi su come compilare un elenco di utenti, vedere [New-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Per visualizzare il nuovo criterio, eseguire `Get-CsExternalAccessPolicy`.


Vedere anche [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy) e [Set-CsExternalAccessPolicy.](/powershell/module/skype/set-csexternalaccesspolicy)

## <a name="common-external-access-scenarios"></a>Scenari comuni di accesso esterno

Le sezioni seguenti descrivono come abilitare la federazione per gli scenari di accesso esterno comuni e in che modo il criterio TeamsUpgradePolicy determina il recapito delle chat e delle chiamate in arrivo.

### <a name="enable-federation"></a>Abilitare la federazione

Per consentire agli utenti dell'organizzazione di comunicare con gli utenti di un'altra organizzazione, entrambe le organizzazioni devono abilitare la federazione. I passaggi per abilitare la federazione per una determinata organizzazione variano a seconda che l'organizzazione sia solo online, ibrida o solo locale.

| Se la propria organizzazione lo è | Abilitare la federazione come segue |
|:---------|:-----------------------|
|Online senza Skype for Business locale. Sono incluse le organizzazioni che hanno utenti TeamsOnly e/o di Skype for Business Online.| Se si usa l'interfaccia di amministrazione di Teams: <br>-   Assicurarsi che i domini con cui si vuole comunicare siano consentiti in Accesso esterno.<br><br>Se si usa PowerShell:<br>- Verificare che il tenant sia abilitato per la federazione: `Get-CsTenantFederationConfiguration` deve mostrare `AllowFederatedUsers=true`. <br>- Verificare che il valore effettivo dell'utente per `CsExternalAccessPolicy` sia `EnableFederationAccess=true`.<br>- Se non si usa la federazione aperta, verificare che il dominio di destinazione sia elencato in `AllowedDomains` di `CsTenantFederationConfiguration`. |
|Solo locale | Negli strumenti locali: <br>- Verificare che la federazione sia abilitata in `CsAccessEdgeConfiguration`.<br>- Verificare che la federazione per l'utente sia abilitata tramite `ExternalAccessPolicy`, mediante criteri globali, criteri del sito o criteri assegnati dall'utente. <br> - Se non si usa la federazione aperta, verificare che il dominio di destinazione sia elencato in `AllowedDomains`. |
|Ibrida con alcuni utenti online (in Skype for Business o Teams) e alcuni utenti in locale. | Seguire i passaggi precedenti per le organizzazioni online e locali. |

### <a name="delivery-of-incoming-chats-and-calls"></a>Recapito di chat e chiamate in entrata 

Le chat e le chiamate in entrata da un'organizzazione della federazione saranno recapitate nel client Teams o Skype for Business dell'utente in base alla modalità dell'utente destinatario in TeamsUpgradePolicy.

| Se si desidera questo | Procedere come segue: |
|:---------|:-----------------------|
| Assicurarsi che le chat e le chiamate federate in entrata arrivino al client Teams dell'utente: | Configurare gli utenti come TeamsOnly.
| Assicurarsi che le chat e le chiamate federate in entrata arrivino al client Skype for Business dell'utente | Configurare gli utenti in modo che siano in qualsiasi modalità tranne TeamsOnly. |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>Abilitare la federazione tra gli utenti dell'organizzazione e gli utenti consumer di Skype

Per abilitare la federazione tra gli utenti dell'organizzazione e gli utenti consumer di Skype:

| Se la propria organizzazione lo è | Abilitare la federazione utente come segue |
|:---------|:-----------------------|
| Solo online senza Skype for Business locale.  Sono incluse le organizzazioni che hanno utenti TeamsOnly e/o di Skype for Business Online. | Se si usa l'interfaccia di amministrazione di Teams: <br>- Assicurarsi che **Consenti agli utenti dell'organizzazione di comunicare con gli utenti Skype** sia abilitato in Accesso esterno.<br><br>Se si usa PowerShell: <br>- Verificare che il tenant sia abilitato per la federazione: `Get-CsTenantFederationConfiguration` deve mostrare `AllowPublicUsers=true`. <br> - Verificare che il valore effettivo dell'utente per `CsExternalAccessPolicy` sia `EnablePublicCloudAccess=true`. |
| Solo locale | Negli strumenti locali: <br> - Verificare che Skype sia abilitato come partner federato. <br> - Verificare che sia impostato `EnablePublicCloudAccess=true` per l'utente tramite `ExternalAccessPolicy`, mediante criteri globali, criteri del sito o criteri assegnati dall'utente.|
| Ibrida con alcuni utenti online (in Skype for Business o Teams) e alcuni utenti in locale.| Seguire i passaggi precedenti per le organizzazioni online e locali.


> [!IMPORTANT]
> Non è necessario aggiungere **domini Skype** come domini consentiti per permettere agli utenti di Teams o Skype for Business Online di comunicare con gli utenti di Skype all'interno o all'esterno dell'organizzazione. **Tutti i domini skype** sono consentiti.

## <a name="federation-diagnostic-tool"></a>Strumento di diagnostica della federazione

Gli amministratori possono usare il seguente strumento di diagnostica per verificare che un utente Teams possa comunicare con un utente Teams federato:

1. Selezionare **Esegui test** di seguito, per popolare la diagnostica nell’interfaccia Amministrazione Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Esegui test: federazione di Teams](https://aka.ms/TeamsFederationDiag)

2. Nel riquadro Esegui diagnostica immettere il **dell'indirizzo SIP (Session Initiation Protocol)** e il **nome di dominio del tenant federato**, quindi selezionare **Esegui test**.

3. I test restituiranno i passaggi da attuare per risolvere eventuali configurazioni del tenant o di criteri che impediscono la comunicazione con l'utente federato.


## <a name="related-topics"></a>Argomenti correlati

- [Esperienza di chat nativa per utenti esterni (federati)](native-chat-for-external-users.md)
