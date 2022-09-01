---
title: Gestire Microsoft 365 e i connettori personalizzati
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come i connettori consentono di mantenere il team aggiornato fornendo spesso contenuti e aggiornamenti direttamente in un canale di Teams per i servizi usati.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8abc7dc981902945cdb8be8ed9a2fe705e0d6e73
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486741"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Gestire Microsoft 365 e i connettori personalizzati

Per mantenere aggiornato il team, i connettori forniscono contenuti di uso frequente e aggiornamenti dei servizi direttamente in un canale di Teams. Con i connettori, gli utenti di Teams possono ricevere aggiornamenti dai servizi più diffusi, come Trello, Wunderlist, GitHub e Azure DevOps Services. Gli aggiornamenti vengono pubblicati direttamente nel flusso di chat del loro team.

I connettori di Microsoft 365 vengono usati sia con Microsoft Teams che con i gruppi di Microsoft 365. Consentono a tutti i membri di rimanere sincronizzati e di ricevere rapidamente le informazioni pertinenti. È possibile usare gli stessi connettori sia in Microsoft Teams che in Microsoft Exchange. Tuttavia, se si disabilitano i connettori configurati per un gruppo di Microsoft 365, verrà anche disabilitata la possibilità di creare connettori da parte del gruppo di Microsoft 365.

Qualsiasi membro di un team può connettere il proprio team ai servizi cloud più diffusi tramite i connettori, se le autorizzazioni del team lo consentono, e tutti i membri del team ricevono una notifica sulle attività del servizio. I connettori continuano a funzionare anche dopo l’uscita del membro che ha inizialmente configurato il connettore. Qualsiasi membro del team con autorizzazioni di aggiunta o rimozione può modificare la configurazione dei connettori da parte di altri membri.

## <a name="enable-or-disable-connectors-in-teams"></a>Abilitare o disabilitare i connettori in Teams

Il modulo PowerShell V2 di Exchange Online usa l'autenticazione moderna e funziona con l'autenticazione a più fattori (MFA) per connettersi a tutti gli ambienti PowerShell correlati a Exchange in Microsoft 365. Gli amministratori possono usare PowerShell per Exchange Online per disabilitare i connettori di un intero tenant o di una cassetta postale di gruppo specifica, influenzando tutti gli utenti del relativo tenant o cassetta postale. Non è possibile disabilitarlo per alcuni utenti specifici. Inoltre, i connettori sono disabilitati per impostazione predefinita per gli ambienti Government Community Cloud (GCC).

> [!NOTE]
> I connettori sono disabilitati per impostazione predefinita negli ambienti Government Cloud Community (GCC). Per abilitarli, impostare i parametri`ConnectorsEnabled` o `ConnectorsEnabledForTeams` su `$true` con il cmdlet `SetOrganizationConfig`. Connettersi a [PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

L'impostazione del tenant esegue l'override dell'impostazione del gruppo. Ad esempio, se un amministratore abilita i connettori per il gruppo e li disabilita nel tenant, i connettori per il gruppo verranno disabilitati. Per abilitare un connettore in Teams, [connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) usando l'autenticazione moderna con o senza MFA.

Per abilitare o disabilitare un connettore, eseguire i comandi seguenti in PowerShell per Exchange Online:

* Per disabilitare i connettori per il tenant: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Per disabilitare i messaggi interattivi per il tenant: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Per abilitare i connettori per Teams, eseguire i comandi seguenti:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Per altre informazioni sullo scambio di moduli in PowerShell, vedere [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Per abilitare o disabilitare i connettori di Outlook, [connettere le app ai gruppi in Microsoft Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

## <a name="publish-connectors-for-your-organization"></a>Pubblicare i connettori per l'organizzazione

Per rendere disponibile un connettore personalizzato agli utenti dell'organizzazione, caricare un'app del connettore personalizzata nel catalogo app dell'organizzazione. Gli utenti finali all'interno dell'organizzazione possono installare, configurare e usare il connettore in un team.

> [!IMPORTANT]
> I connettori personalizzati non sono disponibili negli ambienti Government Community Cloud (GCC), Government Community Cloud-High (GCCH) e Department of Defense (DOD).

Per usare i connettori in un team o in un canale, aprire il menu Altre opzioni nell'angolo in alto a destra di un canale. Nel menu selezionare **Connettori**, quindi individuare o cercare il connettore richiesto. Configurare il connettore selezionato, se necessario.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Aggiungere connettori al canale in Teams da Altre opzioni nell'angolo in alto a destra del canale.":::

## <a name="update-url-of-a-connector"></a>Aggiornare l'URL di un connettore

I connettori di Teams stanno effettuando la transizione verso un nuovo URL per migliorare la sicurezza. Durante la transizione si riceverà una notifica per aggiornare il connettore configurato. Aggiornare il connettore al più presto per evitare qualsiasi interruzione dei relativi servizi. Per aggiornare il connettore:

1. Nella pagina di configurazione dei connettori selezionare il messaggio **È necessario il tuo intervento** accanto al connettore configurato.

   :::image type="content" source="media/teams-attention-required-message.png" alt-text="Screenshot del messaggio È necessario il tuo intervento.":::

1. Per ricreare la connessione per i connettori webhook in ingresso, selezionare **Aggiorna URL** e usare l'URL del webhook generato.

   :::image type="content" source="media/teams-update-url-option.png" alt-text="Screenshot del pulsante Aggiorna URL.":::

1. Per altri tipi di connettore, rimuovere quello corrente e ricreare la configurazione del connettore. Viene visualizzato un **URL aggiornato**.

   :::image type="content" source="media/teams-url-updated.png" alt-text="Lo screenshot dell'URL è un messaggio aggiornato.":::

## <a name="related-articles"></a>Articoli correlati

* [Panoramica su connettori e webhook personalizzati](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Creare connettori di Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
