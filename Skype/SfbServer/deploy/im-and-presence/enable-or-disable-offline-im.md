---
title: Abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Informazioni su come abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server.
ms.openlocfilehash: 02056618aff8a2dcaa6edc2023b67ad38aa9f314
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003046"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="3008f-103">Abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3008f-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="3008f-104">Informazioni su come abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3008f-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="3008f-105">Abilitare la messaggistica istantanea offline in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3008f-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="3008f-106">La messaggistica istantanea offline è una caratteristica lato client integrata nel client Skype for business (2016 C2R Build 16.0.6701.1000 o versione successiva) che sfrutta i servizi Web Exchange (EWS) per inviare messaggi dal client Skype for business alla cassetta postale di Exchange di un utente.</span><span class="sxs-lookup"><span data-stu-id="3008f-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="3008f-107">La messaggistica istantanea offline usa i servizi Web Exchange (EWS) per inviare messaggi offline dal client Skype for business alla cassetta postale del destinatario.</span><span class="sxs-lookup"><span data-stu-id="3008f-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="3008f-108">EWS deve essere disponibile per il client Skype for business per inviare messaggi offline.</span><span class="sxs-lookup"><span data-stu-id="3008f-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="3008f-109">Per altre informazioni sulla pianificazione per la messaggistica istantanea e la presenza, vedere [pianificare la messaggistica istantanea e la presenza in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="3008f-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3008f-110">Se la cassetta postale dell'utente è ospitata in Exchange locale, è necessario il client Skype for business (2016 C2R Build 16.0.6920.1000)</span><span class="sxs-lookup"><span data-stu-id="3008f-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="3008f-111">Per abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3008f-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="3008f-112">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3008f-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="3008f-113">Eseguire il comando seguente per abilitare la messaggistica istantanea offline.</span><span class="sxs-lookup"><span data-stu-id="3008f-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="3008f-114">In Skype for Business Server 2015 CU3 l'opzione EnableOfflineIM è impostata su $True per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3008f-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="3008f-115">Per disabilitare, imposta questo valore su $False.</span><span class="sxs-lookup"><span data-stu-id="3008f-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="3008f-116">Eseguire il comando seguente per verificare che sia impostata la possibilità di archiviare i messaggi istantanei offline.</span><span class="sxs-lookup"><span data-stu-id="3008f-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="3008f-117">Integrazione di messaggistica istantanea offline con Exchange</span><span class="sxs-lookup"><span data-stu-id="3008f-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="3008f-118">La messaggistica istantanea offline non sarà disponibile per i mittenti se ha un criterio client che disabilita il salvataggio automatico dei messaggi offline nella cartella Cronologia conversazioni (EnableIMAutoArchiving = $false).</span><span class="sxs-lookup"><span data-stu-id="3008f-118">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false).</span></span> <span data-ttu-id="3008f-119">Non esiste un meccanismo per verificare se il destinatario è in grado di ricevere messaggi offline.</span><span class="sxs-lookup"><span data-stu-id="3008f-119">There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="3008f-120">Per i messaggi offline inviati all'interno della stessa organizzazione verranno ricevuti come messaggio di posta elettronica con la classe messaggio di messaggistica istantanea. Nota. MissedConversation e verrà incluso nella cartella delle **conversazioni perse** in Outlook, oltre alla cronologia delle conversazioni che verrà ripresa nella scheda cronologia delle conversazioni/elenchi recenti nei client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="3008f-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="3008f-121">Per i messaggi offline inviati dall'organizzazione federata verranno ricevuti come messaggio di posta elettronica senza messaggistica istantanea. Nota. MisssedConversation e non verranno rilevati nelle cartelle della conversazione o della cronologia delle conversazioni perse.</span><span class="sxs-lookup"><span data-stu-id="3008f-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="3008f-122">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="3008f-122">Troubleshooting</span></span>

<span data-ttu-id="3008f-123">C'è un timer da due minuti quando viene inviato un messaggio offline quando viene raccolto ed elaborato.</span><span class="sxs-lookup"><span data-stu-id="3008f-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="3008f-124">Se non è possibile elaborare i messaggi offline, verranno visualizzati nella directory seguente:</span><span class="sxs-lookup"><span data-stu-id="3008f-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="3008f-125">Il log ETL principale di Skype for business conterrà informazioni sull'elaborazione dei messaggi offline ed è l'origine migliore per l'analisi/risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="3008f-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3008f-126">È stato segnalato un problema in cui i messaggi offline non sono stati inviati e la cartella "bozze" è stata riempita con i messaggi.</span><span class="sxs-lookup"><span data-stu-id="3008f-126">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages.</span></span> <span data-ttu-id="3008f-127">Questo problema si verifica con le cassette postali di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="3008f-127">This occurred with Exchange On-Premises mailboxes.</span></span> <span data-ttu-id="3008f-128">Il problema è stato risolto in tutti i canali di C2R a partire da 6/14/2016.</span><span class="sxs-lookup"><span data-stu-id="3008f-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
