---
title: Mascherare i numeri di telefono nelle riunioni di Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come mascherare i numeri di telefono nelle riunioni di Microsoft Teams
ms.openlocfilehash: 5a59ef07873660e79d6c8bc69b7e92095a2fac1a
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726782"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a><span data-ttu-id="14957-103">Mascherare i numeri di telefono nelle riunioni di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14957-103">Mask phone numbers in Microsoft Teams meetings</span></span>

<span data-ttu-id="14957-104">Per una maggior privacy, i numeri di telefono dei partecipanti che a una riunione di Teams con l'audioconferenza vengono visualizzati completamente ai partecipanti interni.</span><span class="sxs-lookup"><span data-stu-id="14957-104">For added privacy, the phone numbers of participants who dial in to a Teams meeting using audio conferencing are fully displayed to the internal participants.</span></span> <span data-ttu-id="14957-105">I numeri vengono mascherati dai partecipanti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14957-105">The numbers are masked from the participants outside of your organization.</span></span> <span data-ttu-id="14957-106">Questa impostazione è l'impostazione predefinita per tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="14957-106">This setting is the default for all organizations.</span></span> <span data-ttu-id="14957-107">Il numero mascherato viene visualizzato come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="14957-107">The masked number is displayed as shown in the following image:</span></span>

![esempio di numero di telefono mascherato](media/hiddenPhoneNum.png)

<span data-ttu-id="14957-109">Per specifici casi d'uso del settore, gli amministratori possono scegliere come visualizzare i numeri di telefono dei partecipanti ai servizi di audioconferenza nelle riunioni organizzate nel tenant.</span><span class="sxs-lookup"><span data-stu-id="14957-109">For specific industry use cases, admins have the ability to choose how the audio conferencing participants' phone numbers appear in meetings that are organized in their tenant.</span></span> <span data-ttu-id="14957-110">Gli amministratori possono scegliere tra tre opzioni:</span><span class="sxs-lookup"><span data-stu-id="14957-110">The admins can choose from three options:</span></span>

- <span data-ttu-id="14957-111">I numeri di telefono sono mascherati solo da partecipanti esterni.</span><span class="sxs-lookup"><span data-stu-id="14957-111">Phone numbers are masked only from external participants.</span></span> <span data-ttu-id="14957-112">I partecipanti che appartengono al tenant dell'organizzatore della riunione continuano a visualizzare il numero di telefono completo.</span><span class="sxs-lookup"><span data-stu-id="14957-112">The participants who belong to the meeting organizer's tenant still see the full phone number.</span></span>
- <span data-ttu-id="14957-113">I numeri di telefono sono mascherati da tutti i partecipanti alla riunione, ad eccezione dell'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="14957-113">Phone numbers are masked from everyone in the meeting except the organizer.</span></span>
- <span data-ttu-id="14957-114">I numeri di telefono vengono smascherati, quindi sono visibili a tutti i partecipanti alla riunione.</span><span class="sxs-lookup"><span data-stu-id="14957-114">Phone numbers are unmasked, which makes them visible to everyone in the meeting.</span></span>

<span data-ttu-id="14957-115">Questa impostazione viene applicata a tutte le superfici della riunione in cui sono esposti i numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="14957-115">This setting is applied to all the surfaces in the meeting where phone numbers are exposed.</span></span>

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a><span data-ttu-id="14957-116">Usare Microsoft PowerShell per impostare il mascheramento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="14957-116">Use Microsoft PowerShell to set phone-number masking</span></span>

<span data-ttu-id="14957-117">Per modificare l'impostazione di mascheramento PSTN (Public Switched Telephone Network), impostare il parametro del **`MaskPstnNumbersType`** cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) su una delle opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="14957-117">To change the Public Switched Telephone Network (PSTN) masking setting, set the **`MaskPstnNumbersType`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to one of the available options.</span></span>

<span data-ttu-id="14957-118">Per mascherare i numeri di telefono solo da partecipanti esterni, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="14957-118">To mask phone numbers only from external participants, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

<span data-ttu-id="14957-119">Per mascherare i numeri di telefono di tutti i partecipanti alla riunione (ad eccezione dell'organizzatore), eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="14957-119">To mask phone numbers from all participants in the meeting (except the organizer), run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

<span data-ttu-id="14957-120">Per disabilitare il mascheramento dei numeri di telefono, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="14957-120">To disable phone number masking, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
