---
title: Gestire l'accesso esterno (Federazione)
author: SerdarSoysal
ms.author: serdars
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
description: L'amministratore IT o di Teams può configurare l'accesso esterno per altri domini (federazione) per consentire agli utenti di tali domini di partecipare a Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 9739c35fcd22229f3f1115edf029535f9b23e8f9
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031782"
---
<a name="manage-external-access-in-microsoft-teams"></a>Gestire l'accesso esterno in Microsoft Teams
======================================================

L'accesso esterno è un modo per gli utenti di team provenienti da un intero dominio esterno per trovare, chiamare, chattare e configurare riunioni con l'utente in teams. È anche possibile usare l'accesso esterno per comunicare con utenti esterni che usano ancora Skype for business (online e locale) e Skype (in anteprima).

> [!NOTE]
> I domini consentiti o bloccati si applicano solo alle riunioni se l'accesso anonimo alle riunioni è "disattivato".

Se si vuole consentire agli utenti esterni di accedere a team e canali, l'accesso guest potrebbe essere un'opzione migliore. Per altre informazioni sulle differenze tra accesso esterno e accesso guest, vedere [Confrontare l'accesso esterno e guest](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Usare l'accesso esterno quando:
  
- Ci sono utenti in diversi domini che hanno bisogno di collaborare. Ad esempio, Pio@contoso.com e Isotta@northwindtraders.com stanno lavorando a un progetto insieme ad altri nei domini contoso.com e northwindtraders.com.

- Si vuole che gli utenti dell'organizzazione usino Teams per contattare persone in specifiche aziende esterne all'organizzazione.

- Si vuole poter essere trovati e contattati da qualsiasi altro utente di Teams al mondo tramite il proprio indirizzo di posta elettronica. 

> [!IMPORTANT]
> Per usare il client teams per comunicare con un utente esterno (se l'utente usa team o Skype for business), l'utente del team deve essere ospitato in Skype for business online.

## <a name="plan-for-external-access"></a>Pianificare l'accesso esterno

L'accesso esterno è attivato per impostazione predefinita in Teams, quindi l'organizzazione può comunicare con tutti i domini esterni. Se si aggiungono domini bloccati, verranno consentiti tutti gli altri domini. Se si aggiungono domini consentiti, tutti gli altri domini verranno bloccati. L'eccezione a questa regola è se i partecipanti anonimi sono consentiti nelle riunioni. Gli scenari per configurare l'accesso esterno nell'interfaccia di amministrazione di Teams ( **Impostazioni organizzazione** > **Accesso esterno** ) sono tre:

- **Federazione aperta** : questa è l'impostazione predefinita in Teams e consente agli utenti dell'organizzazione di trovare, eseguire chiamate, chattare e configurare riunioni con persone esterne all'organizzazione in qualsiasi dominio.

    In questo scenario, gli utenti possono comunicare con tutti i domini esterni che eseguono Teams o Skype for Business E usano la federazione aperta OPPURE hanno aggiunto il dominio al proprio elenco dei consentiti.

- **Consentire domini specifici** : aggiungendo domini a un elenco di **consentiti** è possibile limitare l'accesso esterno solo ai domini consentiti. Dopo aver configurato un elenco di domini consentiti, tutti gli altri domini verranno bloccati. Per consentire domini specifici, fare clic su **Aggiungi un dominio** , aggiungere il nome di dominio, fare clic su **Azione da eseguire sul dominio** e quindi selezionare **Consentito**.

- **Bloccare domini specifici** : l'aggiunta di domini a un elenco di **blocco** è possibile comunicare con tutti i domini esterni *tranne* quelli bloccati. Per bloccare domini specifici, fare clic su **Aggiungi un dominio** , aggiungere il nome di dominio, fare clic su **Azione da eseguire sul dominio** e quindi selezionare **Bloccato**. Dopo aver configurato un elenco di domini bloccati, tutti gli altri domini verranno consentiti.

> [!NOTE]
> Se si disattiva l'accesso esterno nell'organizzazione, gli utenti esterni possono ancora partecipare alle riunioni tramite join anonimo. Per altre informazioni, vedere [gestire le impostazioni delle riunioni in teams](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams).

## <a name="allow-or-block-domains"></a>Consentire o bloccare domini

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>Passaggio 1-consentire all'organizzazione di comunicare con altri team o organizzazioni Skype for business

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro passare a **Impostazioni organizzazione** > **Accesso esterno**.

2. Attivare l'impostazione **Gli utenti possono comunicare con altri utenti di Skype for Business e Teams**.

     ![Screenshot dell'impostazione Gli utenti possono comunicare con altri utenti di Skype for Business e Teams attivata](media/manage-external-access-2.png).

3. Se si vuole consentire a tutte le organizzazioni di Teams di comunicare con gli utenti della propria, andare al passaggio 5.

4. Se si vogliono limitare le organizzazioni che possono comunicare con gli utenti della propria organizzazione, è possibile consentire tutti i domini ad eccezione di alcuni oppure consentire solo domini specifici. 

    - Per consentire tutti i domini tranne alcuni, aggiungere i domini da bloccare facendo clic su **Aggiungi dominio**. Nel riquadro **Aggiungi un dominio** digitare il nome del dominio, fare clic su **Bloccato** e quindi fare clic su **Fatto**. 
    - Per limitare le comunicazioni a organizzazioni specifiche, aggiungere tali domini all'elenco con lo stato **Consentito**. Dopo avere aggiunto un dominio all'elenco dei consentiti, le comunicazioni con altre organizzazioni saranno limitate alle sole organizzazioni i cui domini sono presenti nell'elenco. 

5. Fare clic su **Salva**.

6. Assicurarsi che l'amministratore dell'altra organizzazione di Teams completi gli stessi passaggi. Ad esempio, se l'altro amministratore limita le organizzazioni con cui la sua azienda può comunicare, occorre essere inseriti nel suo elenco dei **domini consentiti**.

### <a name="step-2---test-it"></a>Passaggio 2 - Test

Per testare la configurazione è necessario un utente di Teams che non si trova dietro il proprio firewall aziendale.
  
1. Una volta configurate le impostazioni di **Accesso esterno** in entrambe le organizzazioni, si può procedere.

2. Nell'app Teams cercare l'utente per indirizzo di posta elettronica e inviare una richiesta di chat.

3. Chiedere al contatto di Teams di inviare una richiesta di chat. Se non si riceve la richiesta, il problema sono le impostazioni del firewall, supponendo di aver già verificato che le impostazioni firewall dell'altra organizzazione siano corrette.

4. Un altro modo per verificare se il problema è il firewall consiste nel recarsi in una posizione Wi-Fi non dietro il firewall, ad esempio una caffetteria, e usare Teams per inviare una richiesta di chat al contatto. Se il messaggio viene recapitato nella posizione Wi-Fi, ma non in ufficio, il problema è sicuramente il firewall aziendale.

> [!NOTE]
> Se due organizzazioni attivano l'accesso esterno e consentono i rispettivi domini, tutto funzionerà. In caso contrario, occorre verificare che una delle due configurazioni non stia bloccando l'altro dominio.


## <a name="communicate-with-skype-users-in-preview"></a>Comunicare con gli utenti di Skype (in anteprima)

Seguire questa procedura per consentire agli utenti di Teams nell'organizzazione di comunicare con gli utenti Skype e di chiamarli. Gli utenti di Teams potranno cercare utenti di Skype e avviare una conversazione a due di solo testo oppure una chiamata audio/video e viceversa.

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro passare a **Impostazioni organizzazione** > **Accesso esterno**.

2. Attivare l'impostazione **Gli utenti possono comunicare con gli utenti Skype**.

    ![Screenshot dell'opzione Gli utenti possono comunicare con gli utenti Skype attivata](media/manage-external-access-5.png).

Per altre informazioni sui modi in cui gli utenti di Teams e gli utenti di Skype possono comunicare, incluse le limitazioni applicabili, vedere [Interoperabilità tra Teams e Skype](teams-skype-interop.md).

## <a name="common-external-access-scenarios"></a>Scenari comuni di accesso esterno

Nelle sezioni seguenti viene descritto come abilitare la Federazione per scenari di accesso esterno comuni e come TeamsUpgradePolicy determina il recapito delle chat e delle chiamate in arrivo.

### <a name="enable-federation"></a>Abilitare la Federazione

Per consentire agli utenti dell'organizzazione di comunicare con gli utenti di un'altra organizzazione, entrambe le organizzazioni devono abilitare la Federazione. La procedura per abilitare la Federazione per una determinata organizzazione dipende dal fatto che l'organizzazione sia puramente online, ibrida o puramente locale.

|**Se l'organizzazione è** |**Abilitare la Federazione come segue**  |
|:---------|:-----------------------|
|Online senza Skype for business locale. Sono incluse le organizzazioni che hanno utenti di TeamsOnly e/o utenti Skype for business online.| Se si usa l'interfaccia di amministrazione di teams: <br>-Verificare che gli **utenti possano comunicare con altri utenti di Skype for business e teams per** l'impostazione è abilitato in Access esterno.<br>-Se non si usa la Federazione aperta (che consente la Federazione con qualsiasi altro dominio), aggiungere il dominio esterno all'elenco consentiti.<br><br>Se si usa PowerShell:<br>-Verificare che il tenant sia abilitato per la Federazione: `Get-CsTenantFederationConfiguration` deve essere visualizzato `AllowFederatedUsers=true` . <br>-Verificare che il valore effettivo dell'utente `CsExternalAccessPolicy` sia valido `EnableFederationAccess=true` .<br>-Se non si usa la Federazione aperta, verificare che il dominio di destinazione sia elencato in `AllowedDomains` `CsTenantFederationConfiguration` . |
|Puro locale | In strumenti locali: <br>-Verificare che la Federazione sia abilitata `CsAccessEdgeConfiguration` .<br>-Assicurarsi che la Federazione per l'utente sia abilitata tramite `ExternalAccessPolicy` il criterio globale, i criteri del sito o i criteri assegnati dall'utente. <br> -Se non si usa la Federazione aperta, verificare che il dominio di destinazione sia elencato `AllowedDomains` . |
|Hybrid con alcuni utenti online (sia in Skype for business che in teams) e in alcuni utenti locali. | Seguire i passaggi descritti in precedenza sia per le organizzazioni online che per quelle locali. |

### <a name="delivery-of-incoming-chats-and-calls"></a>Recapito delle chat e delle chiamate in arrivo 

Le chat in arrivo e le chiamate provenienti da un'organizzazione della Federazione sbarcheranno nei team dell'utente o nel client Skype for business, a seconda della modalità dell'utente del destinatario in TeamsUpgradePolicy.

|**Se si vuole** |**Operazione da eseguire:**  |
|:---------|:-----------------------|
| Verificare che le chat e le chiamate federate in arrivo arrivino nel client Teams dell'utente: | Configurare gli utenti in TeamsOnly.
| Verificare che le chat e le chiamate federate in arrivo arrivino nel client Skype for business dell'utente | Configurare gli utenti in modo che siano diversi da TeamsOnly. |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>Abilitare la Federazione tra gli utenti dell'organizzazione e gli utenti consumer di Skype

Per abilitare la Federazione tra gli utenti dell'organizzazione e gli utenti consumer di Skype:

|**Se l'organizzazione è** |**Abilitare la Federazione dei consumi come indicato di seguito**  |
|:---------|:-----------------------|
| Online puro senza Skype for business locale.  Sono incluse le organizzazioni che hanno utenti di TeamsOnly e/o utenti Skype for business online. | Se si usa l'interfaccia di amministrazione di teams: <br>-Verificare che **gli utenti possano comunicare con gli utenti Skype** sia abilitato in Access esterno.<br><br>Se si usa PowerShell: <br>-Verificare che il tenant sia abilitato per la Federazione: `Get-CsTenantFederationConfiguration` deve essere visualizzato `AllowPublicUsers=true` . <br> -Verificare che il valore effettivo dell'utente `CsExternalAccessPolicy` sia valido `EnablePublicCloudAccess=true` . |
| Puro locale | In strumenti locali: <br> -Assicurarsi che Skype sia abilitato come partner federato. <br> -Verificare che `EnablePublicCloudAccess=true` l'utente sia tramite criteri `ExternalAccessPolicy` globali, criteri del sito o criteri assegnati dall'utente.|
| Hybrid con alcuni utenti online (sia in Skype for business che in teams) e in alcuni utenti locali.| Seguire i passaggi descritti in precedenza sia per le organizzazioni online che per quelle locali.


> [!IMPORTANT]
> Non è necessario aggiungere **domini Skype** come domini consentiti per permettere agli utenti di Teams o Skype for Business Online di comunicare gli utenti di Skype all'interno o all'esterno dell'organizzazione. Tutti i **domini Skype** sono inclusi in un elenco dei domini consentiti.

## <a name="how-does-external-access-compare-with-guest-access"></a>Cosa distingue l'accesso esterno dall'accesso guest?

Per informazioni sulla differenza tra accesso esterno e accesso guest, vedere [Comunicare con utenti di altre organizzazioni](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Argomenti correlati

- [Esperienza di chat nativa per utenti esterni (federati)](native-chat-for-external-users.md)
