---
title: Delegare il controllo amministrativo di Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 5c295ed1233cb8a0900828cb1d1c074de1d0f16f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817272"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Delegare il controllo amministrativo di Skype for Business Server 

In Skype for Business Server, le attività amministrative vengono delegate agli utenti usando la funzionalità controllo di accesso basato sui ruoli (RBAC). Quando si installa Skype for Business Server, viene creato un numero di ruoli RBAC. Questi ruoli corrispondono ai gruppi di sicurezza universale in servizi di dominio Active Directory. Ad esempio, il ruolo RBAC CsHelpDesk corrisponde al gruppo CsHelpDesk trovato nel contenitore utenti in servizi di dominio Active Directory. Inoltre, ogni ruolo RBAC è associato a un set di cmdlet di Windows PowerShell per Skype for Business Server. Questi cmdlet rappresentano le attività che possono essere eseguite dagli utenti a cui è stato assegnato il ruolo RBAC specificato. Ad esempio, al ruolo CsHelpDesk sono stati assegnati i cmdlet Lock-CsClientPin e UnlockCsClientPin. Ciò significa che gli utenti a cui è stato assegnato il ruolo CsHelpDesk possono bloccare e sbloccare i numeri di PIN degli utenti. Tuttavia, al ruolo CsHelpDesk non è stato assegnato il cmdlet New-CsVoicePolicy. Ciò significa che gli utenti a cui è stato assegnato il ruolo CsHelpDesk non possono creare nuovi criteri vocali.

## <a name="viewing-information-about-rbac-roles"></a>Visualizzazione delle informazioni sui ruoli RBAC

Puoi recuperare le informazioni di base sui ruoli RBAC eseguendo il comando seguente dall'interno di Skype for Business Server Management Shell:

`Get-CsAdminRole`

Tieni presente che l'identità del ruolo RBAC (ad esempio CsVoiceAdministrator) ha un mapping diretto a un gruppo di sicurezza trovato nel contenitore utenti in servizi di dominio Active Directory.

Per visualizzare un elenco dei cmdlet assegnati a un ruolo, usare un comando simile al seguente:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Assegnazione di un ruolo RBAC a un utente

Per assegnare un ruolo RBAC a un utente, è necessario aggiungere l'utente al gruppo di sicurezza Active Directory appropriato. Ad esempio, per assegnare il ruolo CsLocationAdministrator a un utente, è necessario aggiungere l'utente al gruppo CsLocationAdministrator. Questa operazione può essere eseguita eseguendo la procedura seguente:

1. Utilizzando un account che disponga delle autorizzazioni per modificare l'appartenenza a un gruppo di Active Directory, accedere a un computer in cui sono stati installati utenti e computer di Active Directory.
2. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **utenti e computer di Active Directory**.
3. In utenti e computer di Active Directory espandere il nome del dominio e fare clic sul contenitore **utenti** .
4. Fare clic con il pulsante destro del mouse sul gruppo di sicurezza **CsLocationAdministrator**e quindi scegliere **Proprietà**.
5. Nella scheda **membri** della finestra di dialogo **Proprietà** fare clic su **Aggiungi**.
6. Nella finestra di dialogo **Seleziona utenti, computer, contatti o gruppi** Digitare il nome utente o il nome visualizzato dell'utente da aggiungere al gruppo, ad esempio Ken, nella casella **immettere i nomi degli oggetti da selezionare** e quindi fare clic su **OK**.
7. Nella finestra di dialogo **Proprietà** fare clic su **OK**.

Per verificare che il ruolo RBAC sia stato assegnato, usare il cmdlet Get-CsAdminRoleAssignment, passando il cmdlet SamAccountName (nome accesso Active Directory) dell'utente. Ad esempio, Esegui questo comando dall'interno di Skype for Business Server Management Shell:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
