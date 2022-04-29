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
description: I connettori mantengono il team aggiornato, fornendo contenuto e aggiornamenti provenienti dai servizi usati di frequente direttamente in un canale.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 100db95adf900a48898515b9bb9a3a753b47de4f
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125441"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Gestire Microsoft 365 e connettori personalizzati

Per mantenere aggiornato il team, i connettori forniscono aggiornamenti dei contenuti e dei servizi usati di frequente direttamente in un canale Teams. Con i connettori, gli utenti Teams possono ricevere aggiornamenti dai servizi più diffusi come Trello, Wunderlist, GitHub e Azure DevOps Services. Gli aggiornamenti vengono pubblicati direttamente nel flusso di chat nel team.

Microsoft 365 connettori vengono usati sia con Microsoft Teams che con i gruppi di Microsoft 365, consentendo a tutti i membri di rimanere sincronizzati e ricevere rapidamente le informazioni pertinenti. Sia Microsoft Teams che Exchange utilizzano lo stesso modello di connettore, che consente di utilizzare gli stessi connettori all'interno di entrambe le piattaforme. Tuttavia, se si disabilitano i connettori configurati per un gruppo di Microsoft 365, viene disabilitata anche la possibilità per il gruppo Microsoft 365 di creare connettori.

Qualsiasi membro di un team può connettere il proprio team ai servizi cloud più diffusi con i connettori se le autorizzazioni del team lo consentono e tutti i membri del team ricevono una notifica delle attività di quel servizio. I connettori continuano a funzionare dopo che il membro che ha inizialmente configurato il connettore è rimasto. Qualsiasi membro del team con le autorizzazioni per l'aggiunta o la rimozione può modificare la configurazione dei connettori da parte di altri membri.

## <a name="enable-or-disable-connectors-in-teams"></a>Abilitare o disabilitare i connettori in Teams

Il modulo Exchange Online PowerShell V2 usa l'autenticazione moderna e funziona con l'autenticazione a più fattori, denominata MFA, per la connessione a tutti gli ambienti PowerShell correlati Exchange in Microsoft 365. Gli amministratori possono usare Exchange Online PowerShell per disabilitare i connettori per un intero tenant o una cassetta postale di un gruppo specifico, interessando tutti gli utenti di tale tenant o cassetta postale. Non è possibile disabilitare per pochi utenti specifici. Inoltre, i connettori sono disabilitati per impostazione predefinita per Government Community Cloud, denominati tenant GCC.

L'impostazione tenant sostituisce l'impostazione del gruppo. Ad esempio, se un amministratore abilita i connettori per il gruppo e li disabilita nel tenant, i connettori per il gruppo vengono disabilitati. Per abilitare un connettore in Teams, [connettersi a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) usando l'autenticazione moderna con o senza MFA.

### <a name="commands-to-enable-or-disable-connectors"></a>Comandi per abilitare o disabilitare i connettori

Eseguire i comandi seguenti in Exchange Online PowerShell:

* Per disabilitare i connettori per il tenant: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Per disabilitare i messaggi interattivi per il tenant: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Per abilitare i connettori per Teams, eseguire i comandi seguenti:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Per altre informazioni sullo scambio di moduli di PowerShell, vedere [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Per abilitare o disabilitare i connettori Outlook, [connettere le app ai gruppi in Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

<!---TBD: Delete this section after customer migration to new Webhook URL is complete --->

#### <a name="connector-url-update-notification"></a>Notifica di aggiornamento dell'URL del connettore

I connettori Teams stanno passando a un nuovo URL per migliorare la sicurezza. Durante la transizione, si riceverà una notifica per aggiornare il connettore configurato. Aggiornare il connettore al più presto per evitare interruzioni dei servizi di connettore. Per aggiornare il connettore:

1. Nella pagina di configurazione dei connettori selezionare il messaggio **Attenzione richiesta** accanto al connettore configurato.

   ![Screenshot del messaggio Attenzione richiesta.](media/Teams_Attention_Required_message.png)

1. Per ricreare la connessione per i connettori webhook in ingresso, selezionare **Aggiorna URL** e usare l'URL webhook generato.

   ![Screenshot del pulsante Aggiorna URL.](media/Teams_update_URL_button.png)

1. Per altri tipi di connettore, rimuovere il connettore e ricreare la configurazione del connettore. Viene visualizzato un **URL aggiornato** .

   ![Lo screenshot dell'URL è un messaggio aggiornato.](media/Teams_URL_up_to_date.png)

## <a name="see-also"></a>Vedere anche

* [Panoramica su connettori e webhook personalizzati](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Creare connettori Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)