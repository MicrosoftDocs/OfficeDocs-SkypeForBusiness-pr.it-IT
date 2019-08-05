---
title: Eseguire un'analisi eDiscovery del contenuto in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Informazioni su cosa fare quando è necessario preformare un eDiscovery, ad esempio quando è necessario inviare tutte le info archiviate elettronicamente per il procedimento legale.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54ccb21e33c6acc1747023fc7c3eb174040d5746
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181603"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="055be-103">Eseguire un'analisi eDiscovery del contenuto in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="055be-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="055be-104">Le grandi imprese sono spesso esposte a procedimenti legali di pena elevata che richiedono l'invio di tutte le informazioni archiviate elettronicamente (ESI).</span><span class="sxs-lookup"><span data-stu-id="055be-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="055be-105">Tutti i team 1:1 o chat di gruppo vengono inseriti nelle cassette postali degli utenti e tutti i messaggi di canale vengono inseriti nella cassetta postale del gruppo che rappresenta il team.</span><span class="sxs-lookup"><span data-stu-id="055be-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="055be-106">I file caricati sono coperti dalla funzionalità eDiscovery per SharePoint Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="055be-106">Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="055be-107">Per eseguire un'analisi eDiscovery con il contenuto di Microsoft teams, esaminare [il](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) passaggio 1 in questo collegamento.</span><span class="sxs-lookup"><span data-stu-id="055be-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="055be-108">I dati di Microsoft teams verranno visualizzati come messaggi istantanei o conversazioni nell'output di esportazione di Excel eDiscovery ed è possibile montarlo. PST in Outlook per visualizzare i messaggi dopo l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="055be-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="055be-109">Quando si monta. PST per il team, tenere presente che tutte le conversazioni vengono mantenute nella cartella chat del team in Cronologia conversazioni.</span><span class="sxs-lookup"><span data-stu-id="055be-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="055be-110">Il titolo del messaggio viene allineato al team e al canale.</span><span class="sxs-lookup"><span data-stu-id="055be-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="055be-111">Dalla revisione dell'immagine seguente è possibile visualizzare il messaggio di Roberto che ha inviato un messaggio al canale Project 7 del team di specifiche di manufacturing.</span><span class="sxs-lookup"><span data-stu-id="055be-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Screenshot di una cartella della chat del team nella cassetta postale di un utente in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="055be-113">Per visualizzare le chat private nella cassetta postale di un utente, esse si trovano anche all'interno della cartella chat del team in Cronologia conversazioni.</span><span class="sxs-lookup"><span data-stu-id="055be-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="055be-114">eDiscovery delle chat Guest-to-Guest</span><span class="sxs-lookup"><span data-stu-id="055be-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="055be-115">Senza una cassetta postale, le chat Guest-to-Guest (chat 1xN in cui non ci sono utenti di Home tenant) non verrebbero indicizzate e, di conseguenza, non verrebbero incluse in eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="055be-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="055be-116">Per facilitare eDiscovery per le chat Guest-to-Guest, viene creata una cassetta postale basata sul cloud (o una cassetta postale fantasma) per archiviare i dati di 1xN.</span><span class="sxs-lookup"><span data-stu-id="055be-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="055be-117">Dopo che i dati della chat di teams sono archiviati nella cassetta postale basata sul cloud, è indicizzato per la ricerca di contenuto eDiscovery e conformità.</span><span class="sxs-lookup"><span data-stu-id="055be-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="055be-118">La figura seguente mostra come funziona eDiscovery per le chat Guest-to-Guest in cui non è presente una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="055be-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![Guest-to-Guest-chat-con-senza-cassetta postale](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
