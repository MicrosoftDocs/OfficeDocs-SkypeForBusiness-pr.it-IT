---
title: Configurare le Microsoft 365 Business Voice per gli interventi di emergenza
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Informazioni su come configurare le posizioni di emergenza per Microsoft 365 Business Voice.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 531d1b747a86c84e99c2b6f06a83ae405527f3ba
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130407"
---
# <a name="step-1-set-up-a-business-voice-emergency-location"></a><span data-ttu-id="ea332-103">Passaggio 1: Configurare una posizione di emergenza di Business Voice</span><span class="sxs-lookup"><span data-stu-id="ea332-103">Step 1: Set up a Business Voice emergency location</span></span>

<span data-ttu-id="ea332-104">Una posizione per gli interventi di emergenza viene usata quando qualcuno nell'organizzazione chiama i servizi di emergenza, come il fuoco, la polizia o l'eliambulanza.</span><span class="sxs-lookup"><span data-stu-id="ea332-104">An emergency location is used when someone in your organization calls emergency services such as fire, police, or ambulance.</span></span> <span data-ttu-id="ea332-105">Quando una persona chiama un servizio di emergenza, l'indirizzo configurato come indirizzo di emergenza dell'organizzazione viene inviato al servizio.</span><span class="sxs-lookup"><span data-stu-id="ea332-105">When a person calls an emergency service, the address that's configured as your organization's emergency address is sent to the service.</span></span> <span data-ttu-id="ea332-106">Questo passaggio configura la posizione principale per gli interventi di emergenza per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea332-106">This step sets up the primary emergency location for your organization.</span></span> <span data-ttu-id="ea332-107">Questa posizione verrà associata al numero di telefono principale dell'azienda in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="ea332-107">This location will be associated with your company's main phone number in a later step.</span></span>

<span data-ttu-id="ea332-108">Se si hanno utenti in più posizioni, ad esempio uffici privati o uffici in altre città, è possibile configurare altre posizioni per gli interventi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ea332-108">If you have users in multiple locations, such as home offices or offices in other cities, you can configure additional emergency locations.</span></span> <span data-ttu-id="ea332-109">È anche possibile configurare posizioni specifiche all'interno di una posizione.</span><span class="sxs-lookup"><span data-stu-id="ea332-109">You can even configure specific places within a location.</span></span> <span data-ttu-id="ea332-110">I luoghi possono essere edifici, piani, uffici o altri luoghi in cui gli utenti possono essere in una posizione diversa.</span><span class="sxs-lookup"><span data-stu-id="ea332-110">Places can be different buildings, floors, offices, or other places where users may be at a location.</span></span> <span data-ttu-id="ea332-111">Dopo aver completato la configurazione iniziale di Business Voice, è possibile aggiungere altre posizioni e posizioni.</span><span class="sxs-lookup"><span data-stu-id="ea332-111">Additional locations and places can be added after you complete your initial setup of Business Voice.</span></span>

## <a name="add-an-emergency-location"></a><span data-ttu-id="ea332-112">Aggiungere una posizione per gli interventi di emergenza</span><span class="sxs-lookup"><span data-stu-id="ea332-112">Add an emergency location</span></span>

1. <span data-ttu-id="ea332-113">Aprire [l'Microsoft Teams](https://admin.teams.microsoft.com) di amministrazione ed eseguire l'accesso con un utente che è un amministratore globale (in genere si tratta dell'account usato per iscriversi per Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="ea332-113">Open the [Microsoft Teams admin center](https://admin.teams.microsoft.com) and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="ea332-114">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Posizioni indirizzi**  >  **di emergenza.**</span><span class="sxs-lookup"><span data-stu-id="ea332-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
1. <span data-ttu-id="ea332-115">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ea332-115">Click **Add**.</span></span>
1. <span data-ttu-id="ea332-116">Immettere un nome e una descrizione per la posizione.</span><span class="sxs-lookup"><span data-stu-id="ea332-116">Enter a name and description for the location.</span></span>
1. <span data-ttu-id="ea332-117">Selezionare il paese o l'area geografica e quindi immettere l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="ea332-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ea332-118">In Belgio, Francia, Germania, Irlanda, Paesi Bassi e Spagna è importante comprendere che per attivare correttamente un numero di telefono in Microsoft 365 o Office 365, l'indirizzo configurato nella posizione di emergenza, usata per acquisire il numero, deve corrispondere al codice di area del numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="ea332-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

1. <span data-ttu-id="ea332-119">Se l'indirizzo non viene trovato e si vuole modificarlo manualmente, attivare **Modifica l'indirizzo manualmente.**</span><span class="sxs-lookup"><span data-stu-id="ea332-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
1. <span data-ttu-id="ea332-120">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ea332-120">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ea332-121">Passaggio successivo: Configurare i numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="ea332-121">Next step: Set up phone numbers</span></span>](set-up-phone-numbers.md)
