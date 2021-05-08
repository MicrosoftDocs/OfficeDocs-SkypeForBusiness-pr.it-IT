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
description: Informazioni sull'esperienza Teams chat nativa per gli utenti con accesso esterno (federato) in Microsoft Teams in cui entrambi gli utenti sono in modalità di aggiornamento TeamsOnly.
ms.openlocfilehash: 02bf09a7623079eb207ffca1b122bc03bf07c5c8
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240462"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="6c565-103">Esperienza di chat nativa per utenti esterni (federati) in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c565-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="6c565-104">Quando un Microsoft Teams chatta con un utente esterno (federato), l'esperienza di chat è limitata al testo.</span><span class="sxs-lookup"><span data-stu-id="6c565-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="6c565-105">Tuttavia, se sia l'utente di Teams che la persona di un'altra organizzazione sono in modalità di aggiornamento TeamsOnly, è possibile avere un'esperienza di chat nativa di Teams, che include formattazione avanzata, @mentions e altre funzionalità di chat.</span><span class="sxs-lookup"><span data-stu-id="6c565-105">However, if both your Teams user and the person in another organization are in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="6c565-106">Le Teams chat native con persone di altre organizzazioni sono limitate a 1:1 chat.</span><span class="sxs-lookup"><span data-stu-id="6c565-106">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="6c565-107">L'esperienza di chat nativa per le persone di altre organizzazioni è attivata per tutti Teams tenant, ma non tutte le persone sono idonee.</span><span class="sxs-lookup"><span data-stu-id="6c565-107">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="6c565-108">Per offrire un'esperienza di chat nativa, sia il mittente che il destinatario devono essere configurati per la modalità di aggiornamento TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="6c565-108">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="6c565-109">Per altre informazioni sui criteri di aggiornamento, vedere [Impostazione delle impostazioni di coesistenza e aggiornamento.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6c565-109">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="6c565-110">Per visualizzare un elenco delle funzionalità per gli utenti con accesso esterno in Teams, vedere Confronto tra accesso esterno [e accesso guest.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="6c565-110">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="6c565-111">Come si fa a sapere se si è in una chat nativa?</span><span class="sxs-lookup"><span data-stu-id="6c565-111">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="6c565-112">Se è possibile scambiare testo nella chat solo con persone di altre organizzazioni, si è in una chat standard di accesso esterno (federato).</span><span class="sxs-lookup"><span data-stu-id="6c565-112">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="6c565-113">Se hai altre funzionalità di chat, tra cui formattazione, @mentions, emoji e così via, sei in una chat Teams nativa.</span><span class="sxs-lookup"><span data-stu-id="6c565-113">If you've got other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="6c565-114">Teams controlla periodicamente la modalità di aggiornamento per le persone di altre organizzazioni e, quando trova un Teams che esegue Teams in modalità di aggiornamento TeamsOnly, ti verrà richiesto di passare a una chat Teams nativa e bloccare la chat originale.</span><span class="sxs-lookup"><span data-stu-id="6c565-114">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="6c565-115">Quando si passa a una chat Teams nativa, Teams le due conversazioni non vengono unite.</span><span class="sxs-lookup"><span data-stu-id="6c565-115">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="6c565-116">Al contrario, vedrai entrambe le chat nel feed chat.</span><span class="sxs-lookup"><span data-stu-id="6c565-116">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="6c565-117">La nuova chat nativa Teams è attiva, ma la vecchia chat di solo testo è bloccata.</span><span class="sxs-lookup"><span data-stu-id="6c565-117">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="6c565-118">Cosa succede se un utente non è più in Teams modalità Solo utenti?</span><span class="sxs-lookup"><span data-stu-id="6c565-118">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="6c565-119">Se si aveva una chat Teams nativa con persone di altre organizzazioni e quindi una di queste viene passata dalla modalità di aggiornamento TeamsOnly, Teams blocca la chat nativa di Teams e fornisce un collegamento per una chat limitata di solo testo.</span><span class="sxs-lookup"><span data-stu-id="6c565-119">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="6c565-120">Non sarà possibile continuare nella chat Teams nativa.</span><span class="sxs-lookup"><span data-stu-id="6c565-120">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="6c565-121">È comunque possibile leggere la chat Teams nativa, ma non è possibile continuare la conversazione.</span><span class="sxs-lookup"><span data-stu-id="6c565-121">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="6c565-122">Se Teams trova una vecchia chat di solo testo con questa persona, la rivitalierà.</span><span class="sxs-lookup"><span data-stu-id="6c565-122">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="6c565-123">In caso contrario, Teams crea una nuova chat di solo testo.</span><span class="sxs-lookup"><span data-stu-id="6c565-123">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="6c565-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6c565-124">Related topics</span></span>

[<span data-ttu-id="6c565-125">Gestire l'accesso esterno in Teams</span><span class="sxs-lookup"><span data-stu-id="6c565-125">Manage external access in Teams</span></span>](manage-external-access.md)
