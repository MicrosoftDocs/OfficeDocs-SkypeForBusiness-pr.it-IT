---
title: Criteri di controllo di AppLocker
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come abilitare l'Teams client desktop con i criteri di controllo dell'applicazione AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120848"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="b3a3c-103">Criteri di controllo dell'applicazione AppLocker in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3a3c-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="b3a3c-104">Questo articolo spiega come abilitare l'app client desktop Teams con i criteri di controllo dell'applicazione AppLocker.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="b3a3c-105">L'uso di AppLocker è progettato per limitare l'esecuzione di programmi e script da parte di utenti non amministrativi.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="b3a3c-106">Per altre informazioni e indicazioni su AppLocker, vedere [Che cos'è AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="b3a3c-106">For more information and guidance on AppLocker, see [What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="b3a3c-107">Il processo per l'abilitazione Teams con AppLocker richiede la creazione di criteri di elenchi consentiti basati su AppLocker.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="b3a3c-108">I criteri vengono creati con il software di gestione di Criteri di gruppo e/o l'uso di cmdlet di Windows PowerShell per AppLocker (per altre informazioni, vedere le informazioni di riferimento tecnico su [AppLocker).](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="b3a3c-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="b3a3c-109">I criteri di AppLocker vengono salvati in formato XML e possono essere modificati con qualsiasi editor di testo o XML.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="b3a3c-110">Teams elenco consenti con AppLocker</span><span class="sxs-lookup"><span data-stu-id="b3a3c-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="b3a3c-111">Le regole di AppLocker sono organizzate in raccolte di regole.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="b3a3c-112">Le regole di AppLocker si applicano all'app di destinazione e sono i componenti che costituiscono i criteri di AppLocker.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="b3a3c-113">Per consentire l Teams, è consigliabile [](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) usare le regole delle condizioni dell'autore perché tutti i Teams dell'app sono firmati digitalmente.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-113">To allow Teams, we recommend that you use the [publisher condition rules](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="b3a3c-114">Non è consigliabile usare regole percorso perché la directory Teams di installazione è scrivibile dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="b3a3c-115">È anche sconsigliato l'uso di regole hash perché le regole devono essere aggiornate ogni volta che l'app client Teams viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="b3a3c-116">Poiché Teams file eseguibili desktop sono firmati digitalmente, la condizione dell'autore identifica un file dell'app in base alla firma digitale e agli attributi di versione incorporati.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="b3a3c-117">La firma digitale contiene informazioni sulla società che ha creato il file dell'app (l'autore).</span><span class="sxs-lookup"><span data-stu-id="b3a3c-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="b3a3c-118">Le informazioni sulla versione, ottenute dalla risorsa binaria, includono il nome del prodotto di cui fa parte il file e il numero di versione del file dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="b3a3c-119">Esempio di regole delle condizioni dell'autore</span><span class="sxs-lookup"><span data-stu-id="b3a3c-119">Example of publisher condition rules</span></span>

<span data-ttu-id="b3a3c-120">Per l Teams app client (tutti i file, tutte le versioni) aggiungere quanto segue alle regole eseguibili & DLL:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="b3a3c-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b3a3c-121">Related topics</span></span>
<span data-ttu-id="b3a3c-122">[Che cos'è AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Informazioni di riferimento tecnico su AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="b3a3c-122">[What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>