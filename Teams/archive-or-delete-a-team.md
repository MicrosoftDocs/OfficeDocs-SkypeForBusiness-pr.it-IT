---
title: Archiviare o eliminare un team in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: In questo articolo vengono fornite informazioni su come archiviare o eliminare definitivamente un team in Microsoft teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e17f27cdbaaca9070d87714b58906df96539e12e
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372195"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Archiviare o eliminare un team in Microsoft Teams
===========================================

Nel corso del tempo, un team creato in Microsoft Teams potrebbe non essere più usato o potrebbe essere necessario archiviare o eliminare un team alla fine di un progetto. Se si è un amministratore di Microsoft Teams, seguire i passaggi di questo articolo per archiviare o eliminare un team non più necessario.

Quando avviene l'archiviazione di un team, cessano tutte le attività relative a quel team. L'archiviazione di un team comprende anche i canali privati nel team e le raccolte siti associate.  Tuttavia, è comunque possibile aggiungere o rimuovere membri e aggiornare i ruoli, nonché visualizzare tutte le attività del team in canali, chat e file standard e privati.

Con l'eliminazione di un team, vengono eliminate anche le attività del team in canali, chat e file standard e privati (e nelle raccolte siti associate).

> [!IMPORTANT]
> I team archiviati possono essere riattivati, ma non è possibile ripristinare direttamente un team eliminato. Considerare la possibilità di archiviare prima il team e di posticipare l'eliminazione finché non si è certi di non aver più bisogno del team.

## <a name="archive-a-team"></a>Archiviare un team

Seguire questi passaggi per archiviare un team. Per apportare queste modifiche, è necessario essere un amministratore del servizio teams. Vedere [usare i ruoli di amministratore di team per gestire i team](https://docs.microsoft.com/microsoftteams/using-admin-roles) per leggere informazioni su come ottenere ruoli di amministratore e autorizzazioni.

1. Nell'interfaccia di amministrazione selezionare **Teams**.
2. Selezionare un team facendo clic sul nome del team.
3. Selezionare **Archivia**. Verrà visualizzato il messaggio seguente.

    ![Screenshot del messaggio di archiviazione di Teams](media/teams-archive-message.png)

4. Per impedire agli utenti di modificare il contenuto del sito di SharePoint e della scheda wiki associata al team, selezionare **Rendi il sito di SharePoint di sola lettura per i membri del team**. I proprietari dei team saranno comunque in grado di modificare il contenuto.
5. Selezionare **Archivia** per archiviare il team. Lo stato del team diventerà **Archiviato**.

## <a name="make-an-archived-team-active"></a>Attivare un team archiviato

Seguire questi passaggi per attivare nuovamente un team archiviato.

1. Nell'interfaccia di amministrazione selezionare **Teams**.
2. Selezionare un team facendo clic sul nome del team.
3. Selezionare **Annulla archiviazione**. Lo stato del team diventerà **Attivo**.

## <a name="delete-a-team"></a>Eliminare un team

Se il team non è più necessario, è possibile eseguire l’eliminazione al posto dell’archiviazione. Seguire questi passaggi per eliminare il team.

1.  Nell'interfaccia di amministrazione selezionare **Teams**.
2.  Selezionare un team facendo clic sul nome del team.
3.  Selezionare **Elimina**. Verrà visualizzato un messaggio di conferma.
4.  Selezionare **Elimina** per eliminare definitivamente il team.

## <a name="restore-a-deleted-team"></a>Ripristinare un team eliminato

Seguire questa procedura per ripristinare un team eliminato ripristinando il gruppo Microsoft 365 associato al team. Il ripristino del gruppo Microsoft 365 per un team ripristina il contenuto del team, incluse le schede, i canali standard e i canali privati e le raccolte siti associate.

Per impostazione predefinita, un gruppo Microsoft 365 eliminato viene mantenuto per 30 giorni. Questo periodo di 30 giorni è definito di "eliminazione temporanea", perché è ancora possibile ripristinare il gruppo. Per altre informazioni, vedere [ripristinare un gruppo eliminato](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).

### <a name="install-the-azureadpreview-module"></a>Installare l’anteprima del modulo di Azure AD

1. Aprire Windows PowerShell come amministratore.
2. Se è presente l’installazione di una versione precedente del modulo di Azure AD o di una sua anteprima, disinstallarlo eseguendo una delle operazioni seguenti:

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. Installare la versione più recente dell’anteprima del modulo di Azure AD eseguendo le operazioni seguenti:

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a>Ripristinare il gruppo Microsoft 365 eliminato

1. Connettersi ad Azure AD eseguendo le seguenti operazioni:
    ```PowerShell
    Connect-AzureAD
    ```
    Quando viene richiesto, accedere con l'account e la password di amministratore.  
2. Eseguire la procedura seguente per visualizzare un elenco di tutti i gruppi Microsoft 365 eliminati temporaneamente che si trovano ancora entro il periodo di conservazione di 30 giorni. Utilizzare il parametro **-All $True** se sono presenti molti gruppi.
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. Individuare il gruppo che si vuole ripristinare e quindi prendere nota dell'ID.
4. Eseguire le operazioni seguenti, in cui [Id] è l'ID del gruppo, per ripristinare il gruppo.
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  Eseguire le operazioni seguenti, in cui [Id] è l'ID del gruppo, per verificare che il gruppo sia stato ripristinato correttamente.
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    Il completamento del processo di ripristino può richiedere fino a 24 ore, dopodiché il team e i contenuti associati al team, incluse le schede e i canali, verranno visualizzati in Teams.
