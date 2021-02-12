---
title: Case study su Teams per Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Case study vocale di Teams per multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786036"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="7b896-103">Case study contoso: Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="7b896-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="7b896-104">Per comprendere di cosa si tratta, quali sono i costi, la disponibilità e il funzionamento dei servizi di audioconferenza, Contoso ne ha esaminato il funzionamento &mdash; &mdash; in Office [365.](deploy-audio-conferencing-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="7b896-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="7b896-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="7b896-105">Overview</span></span> 

<span data-ttu-id="7b896-106">Per i servizi di audioconferenza, Contoso ha utilizzato numeri di telefono ben noti sia all'interno che all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7b896-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="7b896-107">Dato che Contoso vuole mantenere questi numeri dove possibile, ha esaminato le informazioni sull'assegnazione di numeri di telefono dedicati e condivisi al bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="7b896-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="7b896-108">In base alle ricerche degli utenti, Contoso ha preso le decisioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b896-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="7b896-109">Solo un segmento della popolazione che ospita regolarmente chiamate in audioconferenza riceverebbe licenze.</span><span class="sxs-lookup"><span data-stu-id="7b896-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="7b896-110">Contoso userebbe numeri di telefono dedicati e porterebbe i numeri esistenti per l'uso con le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="7b896-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="7b896-111">Poiché gli utenti Contoso usavano Skype for Business e le cassette postali di tutti gli utenti risiedono online, molti utenti hanno già pianificato riunioni.</span><span class="sxs-lookup"><span data-stu-id="7b896-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="7b896-112">Contoso ha letto L'uso del servizio [MMS (Meeting Migration Service)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) per sapere che le riunioni esistenti vengono aggiornate automaticamente per Contoso quando l'utente finale imposta la modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="7b896-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="7b896-113">Configurazione</span><span class="sxs-lookup"><span data-stu-id="7b896-113">Configuration</span></span>

<span data-ttu-id="7b896-114">I numeri di telefono associati ai servizi di audioconferenza sono chiamati numeri di servizio all'interno del Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="7b896-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="7b896-115">Per le località che utilizzano i Piani per chiamate, per il portabilità dei numeri di telefono esistenti dal proprio gestore telefonico a Office 365, Contoso ha seguito la procedura descritta in Ottenere numeri di telefono [di servizio.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="7b896-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="7b896-116">Per assegnare la licenza per i servizi di audioconferenza all'utente finale nel progetto pilota tecnico, l'amministratore Contoso ha seguito la procedura descritta in Gestire le impostazioni [di audioconferenza per l'organizzazione.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="7b896-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="7b896-117">Per la distribuzione pilota e la migrazione aziendale, Contoso ha usato le licenze basate sui gruppi seguendo la procedura descritta in Assegnare licenze agli utenti in base all'appartenenza ai gruppi [in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="7b896-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 