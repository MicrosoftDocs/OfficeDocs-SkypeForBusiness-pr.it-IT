---
title: Problemi di ricezione di messaggi e chiamate su sistemi legacy in Teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Risolvere i problemi relativi alla ricezione di messaggi e chiamate in sistemi legacy
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1c209d1acc83e63792722b00b63be5a6b9f3721a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120607"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="bd0ca-103">Problemi con la ricezione di messaggi e chiamate in sistemi legacy</span><span class="sxs-lookup"><span data-stu-id="bd0ca-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="bd0ca-104">Gli utenti potrebbero avere problemi a ricevere messaggi o chiamate se usano versioni precedenti di Teams o hanno eseguito l'accesso con altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="bd0ca-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="bd0ca-105">Configurazioni ADU legacy</span><span class="sxs-lookup"><span data-stu-id="bd0ca-105">Legacy ADU setups</span></span>

 <span data-ttu-id="bd0ca-106">Se gli utenti hanno eseguito l'accesso a un computer aggiunto a un dominio e **non si vuole che il nome utente sia precompilato nella schermata di accesso a Teams**, gli amministratori possono impostare la chiave seguente del Registro di sistema di Windows per disattivare il prepopolamento del nome utente (UPN):</span><span class="sxs-lookup"><span data-stu-id="bd0ca-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="bd0ca-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="bd0ca-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="bd0ca-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="bd0ca-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="bd0ca-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="bd0ca-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="bd0ca-110">La precompilazione del nome utente per i nomi che terminano in ".local" o ".corp" è disattivata per impostazione predefinita, non è necessario impostare una chiave del Registro di sistema allo scopo.</span><span class="sxs-lookup"><span data-stu-id="bd0ca-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="bd0ca-111">Per altre informazioni, vedere Accedere [a Microsoft Teams con l'autenticazione](sign-in-teams.md) moderna.</span><span class="sxs-lookup"><span data-stu-id="bd0ca-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="bd0ca-112">Revoca di token Skype</span><span class="sxs-lookup"><span data-stu-id="bd0ca-112">Skype token revocation</span></span>

<span data-ttu-id="bd0ca-113">Quando si modifica o si reimposta una password, i client meno recenti non riceveranno messaggi e chiamate fino a un'ora.</span><span class="sxs-lookup"><span data-stu-id="bd0ca-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="bd0ca-114">Per risolvere il problema, riavviare l'app o passare ai client più nuovi.</span><span class="sxs-lookup"><span data-stu-id="bd0ca-114">To resolve this issue, either restart the app or move to newer clients.</span></span>


## <a name="related-topics"></a><span data-ttu-id="bd0ca-115">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bd0ca-115">Related topics</span></span>

[<span data-ttu-id="bd0ca-116">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="bd0ca-116">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)