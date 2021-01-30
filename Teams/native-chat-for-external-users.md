---
title: Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni sull'esperienza di chat di Team nativi per gli utenti di Access esterni (federati) in Microsoft teams in cui entrambi gli utenti si trovano nella modalità di aggiornamento di TeamsOnly.
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055658"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="a3372-103">Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a3372-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="a3372-104">Quando un utente di Microsoft teams sta chattando con un utente esterno (federato), l'esperienza della chat è limitata al testo.</span><span class="sxs-lookup"><span data-stu-id="a3372-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="a3372-105">Tuttavia, se sia l'utente del team che la persona in un'altra organizzazione si trova nella modalità di aggiornamento di TeamsOnly, è possibile avere un'"esperienza di chat in team nativi", che include la formattazione RTF, la @mentions e altre funzionalità di chat.</span><span class="sxs-lookup"><span data-stu-id="a3372-105">However, if both your Teams user and the person in another organization is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="a3372-106">In altre parole, puoi avere la stessa esperienza di chat di teams di 1:1 con persone idonee in altre organizzazioni, come hai fatto con gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a3372-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible people in other organizations as you'd have with users in your organization.</span></span> <span data-ttu-id="a3372-107">Le chat di Team native con persone di altre organizzazioni sono limitate solo alle chat di 1:1.</span><span class="sxs-lookup"><span data-stu-id="a3372-107">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="a3372-108">L'esperienza di chat nativa per gli utenti di altre organizzazioni è attivata per tutti i tenant di teams, ma non tutte le persone sono idonee.</span><span class="sxs-lookup"><span data-stu-id="a3372-108">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="a3372-109">Per offrire un'esperienza di chat nativa, sia il mittente che il destinatario devono essere configurati per la modalità di aggiornamento di TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="a3372-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="a3372-110">Per ulteriori informazioni sui criteri di aggiornamento, vedere [impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a3372-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="a3372-111">Per visualizzare un elenco delle funzionalità per gli utenti di Access esterni in teams, vedere [confrontare l'accesso esterno e Guest](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="a3372-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="a3372-112">Come si può verificare se si è in una chat nativa?</span><span class="sxs-lookup"><span data-stu-id="a3372-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="a3372-113">Se è possibile scambiare solo testo in una chat con altri utenti di altre organizzazioni, si è in una chat di accesso esterno standard (federati).</span><span class="sxs-lookup"><span data-stu-id="a3372-113">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="a3372-114">Se si hanno tutte le altre funzionalità di chat, tra cui la formattazione, la @mentions, i emoji e così via, si è in una chat di Team nativi.</span><span class="sxs-lookup"><span data-stu-id="a3372-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="a3372-115">Teams controlla periodicamente la modalità di aggiornamento per gli utenti di altre organizzazioni e, quando trova un gruppo in cui esegue teams nella modalità di aggiornamento di TeamsOnly, ti chiederà di passare a una chat di Team nativi e bloccare la chat originale.</span><span class="sxs-lookup"><span data-stu-id="a3372-115">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="a3372-116">Quando si passa a una chat nativa in teams, i team non uniscono le due conversazioni.</span><span class="sxs-lookup"><span data-stu-id="a3372-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="a3372-117">Verranno invece visualizzate entrambe le chat nel feed della chat.</span><span class="sxs-lookup"><span data-stu-id="a3372-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="a3372-118">La nuova chat a squadre native è attiva, ma la vecchia chat di solo testo è bloccata.</span><span class="sxs-lookup"><span data-stu-id="a3372-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="a3372-119">Cosa succede se un utente non è più in modalità solo Teams?</span><span class="sxs-lookup"><span data-stu-id="a3372-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="a3372-120">Se si sta usando un team nativo per chattare con altre persone in altre organizzazioni e quindi uno di voi viene disattivato dalla modalità di aggiornamento di TeamsOnly, i team bloccano la chat dei team nativi e forniscono un collegamento per una chat limitata di solo testo.</span><span class="sxs-lookup"><span data-stu-id="a3372-120">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="a3372-121">Non potrai continuare nella chat di Team nativi.</span><span class="sxs-lookup"><span data-stu-id="a3372-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="a3372-122">È ancora possibile leggere la chat di Team nativi, ma non è possibile continuare la conversazione.</span><span class="sxs-lookup"><span data-stu-id="a3372-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="a3372-123">Se teams trova una vecchia chat con solo testo con questa persona, la chat verrà riattivata.</span><span class="sxs-lookup"><span data-stu-id="a3372-123">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="a3372-124">In caso contrario, teams crea una nuova chat di solo testo.</span><span class="sxs-lookup"><span data-stu-id="a3372-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a3372-125">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a3372-125">Related topics</span></span>

[<span data-ttu-id="a3372-126">Gestire l'accesso esterno in teams</span><span class="sxs-lookup"><span data-stu-id="a3372-126">Manage external access in Teams</span></span>](manage-external-access.md)
