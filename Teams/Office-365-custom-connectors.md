---
title: Gestire Microsoft 365 e connettori personalizzati
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come i connettori consentono di mantenere il team aggiornato fornendo spesso contenuti e aggiornamenti direttamente in un canale Teams per i servizi usati.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: de0c0398d511aca05a69220e0e35a28268535c59
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190446"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Gestire Microsoft 365 e connettori personalizzati

Per mantenere aggiornato il team, i connettori forniscono aggiornamenti dei contenuti e dei servizi usati di frequente direttamente in un canale Teams. Con i connettori, gli utenti Teams possono ricevere aggiornamenti dai servizi più diffusi come Trello, Wunderlist, GitHub e Azure DevOps Services. Gli aggiornamenti vengono pubblicati direttamente nel flusso di chat nel team.

Microsoft 365 connettori vengono usati sia con Microsoft Teams che con i gruppi di Microsoft 365, consentendo a tutti i membri di rimanere sincronizzati e ricevere rapidamente le informazioni pertinenti. Sia Microsoft Teams che Exchange utilizzano lo stesso modello di connettore, che consente di utilizzare gli stessi connettori all'interno di entrambe le piattaforme. Tuttavia, se si disabilitano i connettori configurati per un gruppo di Microsoft 365, viene disabilitata anche la possibilità per il gruppo Microsoft 365 di creare connettori.

Qualsiasi membro di un team può connettere il proprio team ai servizi cloud più diffusi con i connettori se le autorizzazioni del team lo consentono e tutti i membri del team ricevono una notifica delle attività di quel servizio. I connettori continuano a funzionare dopo che il membro che ha impostato inizialmente il connettore lascia il connettore. Qualsiasi membro del team con le autorizzazioni per l'aggiunta o la rimozione può modificare la configurazione dei connettori da parte di altri membri.

## <a name="enable-or-disable-connectors-in-teams"></a>Abilitare o disabilitare i connettori in Teams

Il modulo Exchange Online PowerShell V2 usa l'autenticazione moderna e funziona con l'autenticazione a più fattori, denominata MFA, per la connessione a tutti gli ambienti PowerShell correlati Exchange in Microsoft 365. Gli amministratori possono usare Exchange Online PowerShell per disabilitare i connettori per un intero tenant o una cassetta postale di un gruppo specifico, interessando tutti gli utenti di tale tenant o cassetta postale. Non è possibile disabilitare per pochi utenti specifici. Inoltre, i connettori sono disabilitati per impostazione predefinita per Government Community Cloud, denominati tenant GCC.

L'impostazione tenant sostituisce l'impostazione del gruppo. Ad esempio, se un amministratore abilita i connettori per il gruppo e li disabilita nel tenant, i connettori per il gruppo vengono disabilitati. Per abilitare un connettore in Teams, [connettersi a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) usando l'autenticazione moderna con o senza MFA.

Per abilitare o disabilitare un connettore, eseguire i comandi seguenti in Exchange Online PowerShell:

* Per disabilitare i connettori per il tenant: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Per disabilitare i messaggi interattivi per il tenant: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Per abilitare i connettori per Teams, eseguire i comandi seguenti:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Per altre informazioni sullo scambio di moduli di PowerShell, vedere [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Per abilitare o disabilitare i connettori Outlook, [connettere le app ai gruppi in Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

<!--- TBD: Find out how can we get to know about completion of customer migration.
Delete this section after customer migration to new Webhook URL is complete.
--->

## <a name="publish-connectors-for-your-organization"></a>Pubblicare connettori per l'organizzazione

Se si vuole che un connettore personalizzato sia disponibile solo per gli utenti dell'organizzazione, è possibile caricare un'app connettore personalizzata nel catalogo app dell'organizzazione. Dopo aver caricato il pacchetto dell'app, gli utenti finali possono installare il connettore dal catalogo app dell'organizzazione e configurare e usare il connettore in un team.

<!---TBD: Check if these instructions are for admins or end-users. I cannot find these options either in Teams or in TAC.

To set up a connector:

1. Select **Apps** from the left navigation bar.
1. In the **Apps** section, select **Connectors**.
1. Select the connector that you want to add.
1. From the pop-up menu, select **Add to a team**.
1. In the search box, type a team or channel name.
1. Select **Set up a Connector** from the pop-up menu in the bottom right corner of the dialog window.
--->

> [!IMPORTANT]
> I connettori personalizzati non sono disponibili in Government Community Cloud (GCC), GCC-High e in Department of Defense (DOD).

Per usare i connettori in un team o in un canale, aprire il menu Altre opzioni nell'angolo in alto a destra di un canale. Nel menu selezionare **Connettori** e quindi individuare o cercare l'app connettore richiesta. Configurare il connettore selezionato, se necessario.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Aggiungere connettori al canale in Teams da Altre opzioni nell'angolo in alto a destra del canale.":::

## <a name="update-url-of-a-connector"></a>Aggiornare l'URL di un connettore

I connettori Teams stanno passando a un nuovo URL per migliorare la sicurezza. Durante la transizione, si riceverà una notifica per aggiornare il connettore configurato. Aggiornare il connettore al più presto per evitare interruzioni dei servizi di connettore. Per aggiornare il connettore:

1. Nella pagina di configurazione dei connettori selezionare il messaggio **Attenzione richiesta** accanto al connettore configurato.

   :::image type="content" source="media/Teams_Attention_Required_message.png" alt-text="Screenshot del messaggio Attenzione richiesta.":::

1. Per ricreare la connessione per i connettori webhook in ingresso, selezionare **Aggiorna URL** e usare l'URL webhook generato.

   :::image type="content" source="media/Teams_update_URL_button.png" alt-text="Screenshot del pulsante Aggiorna URL.":::

1. Per altri tipi di connettore, rimuovere il connettore e ricreare la configurazione del connettore. Viene visualizzato un **URL aggiornato** .

   :::image type="content" source="media/Teams_URL_up_to_date.png" alt-text="Lo screenshot dell'URL è un messaggio aggiornato.":::

## <a name="see-also"></a>Vedere anche

* [Panoramica su connettori e webhook personalizzati](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Creare connettori Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
