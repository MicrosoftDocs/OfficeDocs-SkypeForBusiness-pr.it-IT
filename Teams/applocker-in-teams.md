---
title: Criteri di controllo delle applicazioni di AppLocker in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come abilitare l'applicazione client teams desktop con i criteri di controllo dell'applicazione AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d3e9df38164c5253aab3a331b47b26892a910b7
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826384"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="1ac73-103">Criteri di controllo delle applicazioni di AppLocker in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ac73-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="1ac73-104">Questo articolo spiega come abilitare l'app client desktop teams con i criteri di controllo dell'applicazione AppLocker.</span><span class="sxs-lookup"><span data-stu-id="1ac73-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="1ac73-105">L'uso di AppLocker è progettato per limitare l'esecuzione di programmi e script da parte di utenti non amministrativi.</span><span class="sxs-lookup"><span data-stu-id="1ac73-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="1ac73-106">Per altre informazioni e indicazioni su AppLocker, vedere [che cos'è AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="1ac73-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="1ac73-107">Il processo per l'attivazione di teams con AppLocker richiede la creazione di criteri di whitelist basati su AppLocker.</span><span class="sxs-lookup"><span data-stu-id="1ac73-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="1ac73-108">I criteri vengono creati con il software di gestione di criteri di gruppo e/o l'uso dei cmdlet di Windows PowerShell per AppLocker (per altre informazioni, vedere la [documentazione di riferimento tecnico di AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) ).</span><span class="sxs-lookup"><span data-stu-id="1ac73-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="1ac73-109">I criteri di AppLocker vengono salvati in formato XML e possono essere modificati con qualsiasi testo o editor XML.</span><span class="sxs-lookup"><span data-stu-id="1ac73-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="1ac73-110">Whitelist delle squadre con AppLocker</span><span class="sxs-lookup"><span data-stu-id="1ac73-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="1ac73-111">Le regole di AppLocker sono organizzate in insiemi di regole.</span><span class="sxs-lookup"><span data-stu-id="1ac73-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="1ac73-112">Le regole di AppLocker si applicano all'app di destinazione e sono i componenti che costituiscono i criteri di AppLocker.</span><span class="sxs-lookup"><span data-stu-id="1ac73-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="1ac73-113">Per i team whitelist, ti consigliamo di usare le [regole della condizione di Publisher](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , poiché tutti i file dell'app teams sono firmati digitalmente.</span><span class="sxs-lookup"><span data-stu-id="1ac73-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="1ac73-114">Non è consigliabile usare le regole di percorso perché la directory di installazione di teams è scrivibile dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1ac73-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="1ac73-115">Non è inoltre consigliabile usare le regole hash perché le regole devono essere aggiornate ogni volta che viene aggiornata l'app client teams.</span><span class="sxs-lookup"><span data-stu-id="1ac73-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="1ac73-116">Dato che i file eseguibili desktop di teams sono firmati digitalmente, la condizione di Publisher identifica un file dell'app in base alla firma digitale e agli attributi della versione incorporata.</span><span class="sxs-lookup"><span data-stu-id="1ac73-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="1ac73-117">La firma digitale contiene informazioni sulla società che ha creato il file dell'app (l'editore).</span><span class="sxs-lookup"><span data-stu-id="1ac73-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="1ac73-118">Le informazioni sulla versione, ottenute dalla risorsa binaria, includono il nome del prodotto in cui il file fa parte e il numero di versione del file dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1ac73-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="1ac73-119">Esempio di regole della condizione di Publisher</span><span class="sxs-lookup"><span data-stu-id="1ac73-119">Example of publisher condition rules</span></span>

<span data-ttu-id="1ac73-120">Per l'app client Teams (tutti i file, tutte le versioni) aggiungere quanto segue alle regole eseguibili & regole della DLL:</span><span class="sxs-lookup"><span data-stu-id="1ac73-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="1ac73-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1ac73-121">Related topics</span></span>
<span data-ttu-id="1ac73-122">[Che cos'è AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
Informazioni di [riferimento tecnico su AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="1ac73-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>
