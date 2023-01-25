---
title: Gestire i connettori e i connettori personalizzati di Microsoft 365
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 01/24/2023
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come i connettori consentono di mantenere aggiornato il team distribuendo spesso contenuti e aggiornamenti direttamente in un canale di Teams per i servizi usati.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf38711da0205e7c674e769942d00d340d51f66e
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983684"
---
# <a name="manage-microsoft-365-connectors-and-custom-connectors"></a>Gestire i connettori e i connettori personalizzati di Microsoft 365

I connettori in Microsoft Teams forniscono aggiornamenti dei contenuti e dei servizi direttamente dai servizi di terze parti in un canale di Teams. Usando i connettori, gli utenti ricevono gli aggiornamenti dai servizi più diffusi come Trello, Wunderlist, GitHub e Azure DevOps Services. Gli aggiornamenti vengono pubblicati direttamente nel flusso di chat. In questo modo tutti i membri possono rimanere sincronizzati e ricevere rapidamente le informazioni pertinenti.

I connettori Microsoft 365 vengono usati sia con Teams che con i gruppi di Microsoft 365. È possibile usare gli stessi connettori in Teams e Microsoft Exchange. 

<!--- However, if you disable any connectors configured for a Microsoft 365 group, it also disables the ability for the Microsoft 365 group to create connectors. --->

Se le autorizzazioni del team lo consentono, qualsiasi membro di un team può aggiungere un connettore nel team e tutti i membri del team riceveno una notifica delle attività di quel servizio. Qualsiasi membro del team con autorizzazioni di aggiunta o rimozione può modificare la configurazione dei connettori da parte di altri membri.

## <a name="enable-or-disable-connectors-in-teams"></a>Abilitare o disabilitare i connettori in Teams

Il modulo Exchange Online PowerShell v2 usa l'autenticazione moderna e funziona con l'autenticazione a più fattori (MFA) per connettersi a tutti gli ambienti PowerShell correlati a Exchange in Microsoft 365. Gli amministratori possono usare PowerShell per Exchange Online per disabilitare i connettori di un intero tenant o di una cassetta postale di gruppo specifica, influenzando tutti gli utenti del relativo tenant o cassetta postale. Non è possibile disabilitare alcuni utenti specifici.

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

## <a name="considerations-when-using-connectors-in-teams"></a>Considerazioni sull'uso dei connettori in Teams

* I connettori sono disabilitati per impostazione predefinita negli ambienti Government Cloud Community (GCC). Per abilitarli, impostare i parametri`ConnectorsEnabled` o `ConnectorsEnabledForTeams` su `$true` con il cmdlet `SetOrganizationConfig`. Connettersi a [PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

* Se l'utente che ha aggiunto un connettore a un team lascia il team, il connettore continua a funzionare.

* I connettori seguenti non sono disponibili a partire da gennaio 2023:

  * AHA
  * AIRBRAKE
  * AIRCALL
  * APPLINKS
  * APPSIGNAL
  * FAGIOLO MAGICO
  * BITBUCKET
  * BITBUCKETSERVER
  * AMICO
  * BUGSNAG
  * BUILDKITE
  * CATSONE
  * CHATRA
  * CIRCLECI
  * CODESHIP
  * GETRESPONSE
  * GHOSTINSPECTOR
  * GROOVE
  * HEROKU
  * HONEYBADGER
  * CITOFONO
  * LOGENTRIES
  * NUOVORELIC
  * OPSGENIE
  * PAGERDUTY
  * PAPERTRAIL
  * PINGDOM
  * PIVOTALTRACKER
  * RAYGUN
  * ROLLBAR
  * RUNSCOPE
  * SATISMETER
  * SEMAFORO
  * SENTINELLA
  * SHAREPOINTNEWS
  * SIMPLEINOUT
  * STATUSPAGEIO
  * SUBVERSION
  * TEAMFOUNDATIONSERVER
  * TESTFAIRY
  * TRAVISCI
  * UPDOWN
  * USERLIKE
  * XPDEV

## <a name="related-articles"></a>Articoli correlati

* [Panoramica di connettori e webhook personalizzati](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Come creare connettori Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
