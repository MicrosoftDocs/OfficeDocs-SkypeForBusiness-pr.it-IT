---
title: Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni sull'esperienza di chat di Team native per utenti di Access esterni (federati) in Microsoft teams, disponibile tra utenti esterni in cui entrambi gli utenti si trovano nella modalità di aggiornamento di TeamsOnly.
ms.openlocfilehash: 1274e71f5854e05049c8d766bd3456a0792b1032
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583845"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="60e39-103">Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60e39-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>
======================================

<span data-ttu-id="60e39-104">Quando un utente di Microsoft teams sta chattando con un utente esterno (federato), l'esperienza della chat è limitata al testo.</span><span class="sxs-lookup"><span data-stu-id="60e39-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="60e39-105">Tuttavia, se sia l'utente del team che l'utente esterno si trova nella modalità di aggiornamento di TeamsOnly, è possibile avere un'"esperienza di chat con Team nativi", che include la formattazione RTF, la @mentions e altre funzionalità di chat.</span><span class="sxs-lookup"><span data-stu-id="60e39-105">However, if both your Teams user and the external user is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="60e39-106">In altre parole, puoi avere la stessa esperienza di chat di Microsoft teams Rich 1:1 con utenti esterni idonei, come hai fatto con gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="60e39-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible external users as you'd have with users in your organization.</span></span> <span data-ttu-id="60e39-107">Le chat di teams native con utenti esterni sono ancora limitate solo alle chat di 1:1 (gli utenti esterni non possono eseguire chat di gruppo).</span><span class="sxs-lookup"><span data-stu-id="60e39-107">Native Teams chats with external users are still limited to 1:1 chats only (external users can't do group chats).</span></span>

<span data-ttu-id="60e39-108">L'esperienza di chat nativa per gli utenti esterni è attivata per tutti i tenant di teams, ma non tutti gli utenti sono idonei.</span><span class="sxs-lookup"><span data-stu-id="60e39-108">The native chat experience for external users is turned on for all Teams tenants, but not all users are eligible.</span></span> <span data-ttu-id="60e39-109">Per offrire un'esperienza di chat nativa, sia il mittente che il destinatario devono essere configurati per la modalità di aggiornamento di TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="60e39-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="60e39-110">Per ulteriori informazioni sui criteri di aggiornamento, vedere [impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="60e39-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="60e39-111">Per visualizzare un elenco delle funzionalità per gli utenti di Access esterni in teams, vedere [confrontare l'accesso esterno e Guest](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="60e39-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="60e39-112">Come si può verificare se si è in una chat nativa?</span><span class="sxs-lookup"><span data-stu-id="60e39-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="60e39-113">Se è possibile scambiare solo testo in una chat con un utente esterno, si è in una chat di accesso esterno standard (federati).</span><span class="sxs-lookup"><span data-stu-id="60e39-113">If you can only exchange text in your chat with an external user, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="60e39-114">Se hai tutte le altre funzionalità di chat, inclusi la formattazione, la @mentions, i emoji e così via, sei in una chat di Team nativi con l'utente esterno.</span><span class="sxs-lookup"><span data-stu-id="60e39-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat with your external user.</span></span> 

<span data-ttu-id="60e39-115">Teams controlla periodicamente la modalità di aggiornamento per gli utenti esterni e, quando trova un utente esterno che esegue teams nella modalità di aggiornamento di TeamsOnly, verrà chiesto di passare a una chat di Team nativi e bloccare la chat originale.</span><span class="sxs-lookup"><span data-stu-id="60e39-115">Teams periodically checks the upgrade mode for external users and, when it finds an external user running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="60e39-116">Quando si passa a una chat nativa in teams, i team non uniscono le due conversazioni.</span><span class="sxs-lookup"><span data-stu-id="60e39-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="60e39-117">Verranno invece visualizzate entrambe le chat nel feed della chat.</span><span class="sxs-lookup"><span data-stu-id="60e39-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="60e39-118">La nuova chat a squadre native è attiva, ma la vecchia chat di solo testo è bloccata.</span><span class="sxs-lookup"><span data-stu-id="60e39-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="60e39-119">Cosa succede se un utente non è più in modalità solo Teams?</span><span class="sxs-lookup"><span data-stu-id="60e39-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="60e39-120">Se si sta usando una chat di Team nativi con un utente esterno e uno di essi viene disattivato dalla modalità di aggiornamento di TeamsOnly, i team bloccano la chat dei team nativi e forniscono un collegamento per una chat limitata di solo testo.</span><span class="sxs-lookup"><span data-stu-id="60e39-120">If you were having a native Teams chat with an external user and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="60e39-121">Non potrai continuare nella chat di Team nativi.</span><span class="sxs-lookup"><span data-stu-id="60e39-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="60e39-122">È ancora possibile leggere la chat di Team nativi, ma non è possibile continuare la conversazione.</span><span class="sxs-lookup"><span data-stu-id="60e39-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="60e39-123">Se teams trova una vecchia chat di solo testo con questo utente esterno, la chat verrà riattivata.</span><span class="sxs-lookup"><span data-stu-id="60e39-123">If Teams finds an old text-only chat with this external user, it'll revive that chat.</span></span> <span data-ttu-id="60e39-124">In caso contrario, teams crea una nuova chat di solo testo.</span><span class="sxs-lookup"><span data-stu-id="60e39-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="60e39-125">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="60e39-125">Related topics</span></span>

[<span data-ttu-id="60e39-126">Gestire l'accesso esterno in teams</span><span class="sxs-lookup"><span data-stu-id="60e39-126">Manage external access in Teams</span></span>](manage-external-access.md)
