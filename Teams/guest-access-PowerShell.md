---
title: Usare PowerShell per controllare l'accesso Guest a un team
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Usare PowerShell per consentire o bloccare l'accesso Guest ai team in Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e106dc56f56b5e26dd56384931deeecdd889305
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235879"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Usare PowerShell per controllare l'accesso Guest a un team
================================================

Oltre a usare l'interfaccia di amministrazione di Microsoft 365 e il portale di Azure Active Directory (Azure AD), è possibile usare Windows PowerShell per controllare l'accesso guest. Con PowerShell è possibile eseguire le operazioni seguenti:
  
- Consentire o bloccare l'accesso Guest a tutti i team e gruppi di Office 365

- Consentire l'aggiunta di Guest a tutti i team e gruppi di Office 365

- Consentire o bloccare gli utenti Guest da un team specifico o da un gruppo di Office 365

Per informazioni dettagliate, vedere "usare PowerShell per controllare l'accesso guest" in [gestire l'accesso guest nei gruppi di Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).
  
È anche possibile usare PowerShell per consentire o bloccare un utente guest in base al proprio dominio. Ad esempio, supponiamo che la tua azienda (contoso) abbia una partnership con un'altra azienda (Fabrikam). È possibile aggiungere Fabrikam all'elenco consentiti in modo che gli utenti possano aggiungere tali Guest ai rispettivi gruppi. Per altre informazioni, vedere [consentire/bloccare l'accesso Guest ai gruppi di Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Se si vuole bloccare gli ospiti in teams e si vuole comunque consentire loro di accedere ai siti di SharePoint, è possibile usare i cmdlet di Azure AD PowerShell per disabilitare il parametro AllowGuestsToAccessGroups nell'oggetto società, presupponendo che la condivisione esterna sia attivata per i siti di SharePoint .

## <a name="guest-access-vs-external-access"></a>Accesso guest e accesso esterno

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
