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
description: Informazioni sull'esperienza di chat nativa di Teams per gli utenti di accesso esterno (federato) in Microsoft Teams, in cui entrambi gli utenti sono in modalità di aggiornamento TeamsOnly.
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055658"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="85ec1-103">Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85ec1-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="85ec1-104">Quando un utente di Microsoft Teams chatta con un utente esterno (federato), l'esperienza di chat è limitata al testo.</span><span class="sxs-lookup"><span data-stu-id="85ec1-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="85ec1-105">Tuttavia, se sia l'utente di Teams che la persona in un'altra organizzazione si trova nella modalità di aggiornamento di TeamsOnly, è possibile avere un'esperienza di chat nativa di Teams, che include formattazione avanzata, @mentions e altre funzionalità di chat.</span><span class="sxs-lookup"><span data-stu-id="85ec1-105">However, if both your Teams user and the person in another organization is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="85ec1-106">In altre parole, puoi avere la stessa ricca esperienza di chat 1:1 Teams con persone idonee in altre organizzazioni come faresti con gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="85ec1-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible people in other organizations as you'd have with users in your organization.</span></span> <span data-ttu-id="85ec1-107">Le chat native di Teams con persone in altre organizzazioni sono limitate a chat 1:1.</span><span class="sxs-lookup"><span data-stu-id="85ec1-107">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="85ec1-108">L'esperienza di chat nativa per le persone in altre organizzazioni è attivata per tutti i tenant di Teams, ma non tutte le persone sono idonee.</span><span class="sxs-lookup"><span data-stu-id="85ec1-108">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="85ec1-109">Per offrire un'esperienza di chat nativa, è necessario configurare sia il mittente che il destinatario per la modalità di aggiornamento TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="85ec1-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="85ec1-110">Per altre informazioni sui criteri di aggiornamento, vedere [Impostazione delle impostazioni di coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="85ec1-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="85ec1-111">Per visualizzare un elenco di funzionalità per gli utenti con accesso esterno in Teams, vedere [Confrontare l'accesso esterno e guest.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="85ec1-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="85ec1-112">Come faccio a sapere se sono in una chat nativa?</span><span class="sxs-lookup"><span data-stu-id="85ec1-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="85ec1-113">Se è possibile scambiare testo solo nella chat con persone di altre organizzazioni, si è in una chat di accesso esterno (federato) standard.</span><span class="sxs-lookup"><span data-stu-id="85ec1-113">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="85ec1-114">Se hai tutte le altre funzionalità di chat, tra cui la formattazione, @mentions, emoji e così via, sei in una chat nativa di Teams.</span><span class="sxs-lookup"><span data-stu-id="85ec1-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="85ec1-115">Teams controlla periodicamente la modalità di aggiornamento per le persone in altre organizzazioni e, quando trova un team che esegue Teams in modalità di aggiornamento TeamsOnly, ti chiederà di passare a una chat nativa di Teams e bloccare la chat originale.</span><span class="sxs-lookup"><span data-stu-id="85ec1-115">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="85ec1-116">Quando si passa a una chat nativa di Teams, Teams non unisce le due conversazioni.</span><span class="sxs-lookup"><span data-stu-id="85ec1-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="85ec1-117">Verranno invece visualizzati entrambe le chat nel feed chat.</span><span class="sxs-lookup"><span data-stu-id="85ec1-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="85ec1-118">La nuova chat nativa di Teams è attiva, ma la vecchia chat di solo testo è bloccata.</span><span class="sxs-lookup"><span data-stu-id="85ec1-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="85ec1-119">Cosa succede se un utente non è più in modalità Solo teams?</span><span class="sxs-lookup"><span data-stu-id="85ec1-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="85ec1-120">Se si aveva una chat nativa di Teams con persone di altre organizzazioni e quindi una di queste viene passata dalla modalità di aggiornamento TeamsOnly, Teams blocca la chat nativa di Teams e fornisce un collegamento per una chat limitata di solo testo.</span><span class="sxs-lookup"><span data-stu-id="85ec1-120">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="85ec1-121">Non sarà possibile continuare nella chat nativa di Teams.</span><span class="sxs-lookup"><span data-stu-id="85ec1-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="85ec1-122">È comunque possibile leggere la chat nativa di Teams, ma non è possibile continuare la conversazione.</span><span class="sxs-lookup"><span data-stu-id="85ec1-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="85ec1-123">Se Teams trova una vecchia chat solo testuale con questa persona, la chat verrà ripristinata.</span><span class="sxs-lookup"><span data-stu-id="85ec1-123">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="85ec1-124">In caso contrario, Teams crea una nuova chat solo testuale.</span><span class="sxs-lookup"><span data-stu-id="85ec1-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="85ec1-125">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="85ec1-125">Related topics</span></span>

[<span data-ttu-id="85ec1-126">Gestire l'accesso esterno in Teams</span><span class="sxs-lookup"><span data-stu-id="85ec1-126">Manage external access in Teams</span></span>](manage-external-access.md)
