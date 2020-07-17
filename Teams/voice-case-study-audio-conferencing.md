---
title: Case Study di teams Voice contoso
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
description: Case Study di teams Voice per società multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786036"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="e5532-103">Case Study di Contoso: Servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="e5532-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="e5532-104">Per ottenere una conoscenza dei servizi di audioconferenza, quali sono i &mdash; costi, la disponibilità e la modalità di funzionamento di servizi di audioconferenza &mdash; recensiti da Contoso [in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="e5532-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="e5532-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e5532-105">Overview</span></span> 

<span data-ttu-id="e5532-106">Per i servizi di audioconferenza, Contoso ha usato i numeri di telefono ben noti all'interno dell'organizzazione e esternamente.</span><span class="sxs-lookup"><span data-stu-id="e5532-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="e5532-107">Poiché Contoso ha voluto mantenere questi numeri, se possibile, hanno esaminato le informazioni sull'assegnazione di numeri di telefono dedicati e condivisi al Bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="e5532-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="e5532-108">In base alle proprie ricerche, Contoso ha preso le decisioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5532-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="e5532-109">Solo un segmento della popolazione che ospita regolarmente le chiamate di audioconferenza riceverebbe licenze per le conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="e5532-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="e5532-110">Contoso utilizzerà numeri di telefono dedicati e trasferirà i numeri esistenti per l'uso con i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="e5532-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="e5532-111">Poiché gli utenti di Contoso usano Skype for business e tutte le cassette postali degli utenti si trovano online, molti utenti hanno pianificato riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="e5532-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="e5532-112">Contoso ha letto [usando il servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) per scoprire che le riunioni esistenti vengono aggiornate automaticamente per contoso quando modificano l'utente finale in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e5532-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="e5532-113">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e5532-113">Configuration</span></span>

<span data-ttu-id="e5532-114">I numeri di telefono associati ai servizi di audioconferenza sono indicati come numeri di servizio all'interno del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="e5532-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="e5532-115">Per le posizioni che usano piani di chiamata, per trasferire i numeri di telefono esistenti dal proprio gestore telefonico a Office 365, Contoso ha seguito i passaggi per [ottenere i numeri di telefono del servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="e5532-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="e5532-116">Per assegnare la licenza di audioconferenza all'utente finale nel Pilot tecnico, l'amministratore di Contoso ha seguito la procedura descritta in [gestire le impostazioni di audioconferenza per l'organizzazione](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e5532-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="e5532-117">Per il pilota aziendale e la migrazione, Contoso ha usato le licenze basate su gruppi seguendo la procedura descritta in [assegnare licenze agli utenti per appartenenza al gruppo in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="e5532-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 