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
description: Informazioni su come archiviare o eliminare definitivamente un team.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30913e67c80f5f5e8c04ddf5d7855dcf25536834
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992906"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Archiviare o eliminare un team in Microsoft Teams
===========================================

Nel corso del tempo, un team creato in Microsoft teams potrebbe non essere in uso oppure potrebbe essere necessario archiviare o eliminare un team alla fine di un progetto. Se si è un amministratore di Microsoft teams, seguire i passaggi di questo articolo per archiviare o eliminare un team non più necessario.

Quando si archivia un team, tutte le attività per il team cessano. L'archiviazione di un team archivia anche i canali privati nel team e le raccolte siti associate.  Tuttavia, è comunque possibile aggiungere o rimuovere membri e aggiornare ruoli ed è comunque possibile visualizzare tutte le attività del team in canali, file e chat standard e privati.

Quando si elimina un team, viene eliminata anche l'attività del team in canali standard e privati (e le raccolte siti associate), i file e le chat.

> [!IMPORTANT]
> I team archiviati possono essere riattivati, ma non è possibile ripristinare direttamente un team che è stato eliminato. È consigliabile archiviare prima di tutto il team e posticipare l'eliminazione finché non si è certi di non avere più bisogno del team.

## <a name="archive-a-team"></a>Archiviare un team

Seguire questa procedura per archiviare un team.

1. Nell'interfaccia di amministrazione di Microsoft teams selezionare **Teams**.
2. Selezionare un team facendo clic sul nome del team.
3. Selezionare **Archivia**. Verrà visualizzato il messaggio seguente.

    ![Screenshot del messaggio di archivio di Teams](media/teams-archive-message.png)

4. Se si vuole rendere il sito di SharePoint per il team di sola lettura, selezionare la casella di controllo.
5. Selezionare **Archivia** per archiviare il team. Lo stato del team cambierà in **archiviato**.

## <a name="make-an-archived-team-active"></a>Rendere attivo un team archiviato

Seguire questa procedura per rendere nuovamente attivo un team archiviato.

1. Nell'interfaccia di amministrazione di Microsoft teams selezionare **Teams**.
2. Selezionare un team facendo clic sul nome del team.
3. Selezionare **Archivia**. Lo stato del team cambierà in **attivo**.

## <a name="delete-a-team"></a>Eliminare un team

Se il team non sarà necessario in futuro, è possibile eliminarlo invece di archiviarlo. Seguire questa procedura per eliminare un team.

1.  Nell'interfaccia di amministrazione di Microsoft teams selezionare **Teams**.
2.  Selezionare un team facendo clic sul nome del team.
3.  Selezionare **Elimina**. Verrà visualizzato un messaggio di conferma.
4.  Selezionare **Elimina** per eliminare definitivamente il team.

## <a name="restore-a-deleted-team"></a>Ripristinare un team eliminato

Seguire questa procedura per ripristinare un team eliminato ripristinando il gruppo di Office 365 associato al team. Il ripristino del gruppo Office 365 per un team, ripristina il contenuto del team, incluse le schede, i canali standard e i canali privati e le raccolte siti associate.

Per impostazione predefinita, un gruppo di Office 365 eliminato viene mantenuto per 30 giorni. Questo periodo di 30 giorni si chiama "soft-delete" perché è possibile ripristinare il gruppo. Per altre informazioni, vedere [ripristinare un gruppo di Office 365 eliminato](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group).

### <a name="install-the-azureadpreview-module"></a>Installare il modulo AzureADPreview

1. Aprire Windows PowerShell come amministratore.
2. Se è installata una versione precedente del modulo AzureADPreview o se è installato il modulo AzureAD, disinstallarlo eseguendo una delle operazioni seguenti:

    ```PowerShell 
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. Installare la versione più recente del modulo AzureADPreview eseguendo le operazioni seguenti:

    ```PowerShell
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a>Ripristinare il gruppo di Office 365 eliminato

1. Connettersi a Azure AD eseguendo le operazioni seguenti:
    ```PowerShell
    Connect-AzureAD
    ```
    Quando viene richiesto, accedere con l'account di amministratore e la password.  
2. Eseguire la procedura seguente per visualizzare un elenco di tutti i gruppi di Office 365 eliminati temporaneamente che si trovano ancora entro il periodo di conservazione di 30 giorni. Usa il parametro **-All $True** se hai molti gruppi.
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. Individuare il gruppo che si vuole ripristinare e quindi prendere nota dell'ID.
4. Eseguire la procedura seguente per ripristinare il gruppo, dove [ID] è l'ID del gruppo.
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  Eseguire la procedura seguente per verificare che il gruppo sia stato ripristinato correttamente, dove [ID] è l'ID del gruppo.
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    Il completamento del processo di ripristino può richiedere fino a 24 ore, dopodiché il team e il contenuto associato al team, incluse le schede e i canali, vengono visualizzati in teams.
