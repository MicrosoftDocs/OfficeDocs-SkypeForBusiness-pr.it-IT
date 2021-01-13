---
title: Procedure consigliate per l'infrastruttura di base in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: È probabile che siano già state intraprese azioni per progettare la tolleranza di errore nel sistema, ad esempio garantendo la ridondanza hardware, prendendo precauzioni in caso di interruzioni dell'alimentazione, installando con regolarità gli aggiornamenti antivirus e della sicurezza e monitorando l'attività dei server. Queste procedure non sono utili solo per l'infrastruttura di Skype for Business Server, ma anche per l'intera rete. Se non sono state implementate queste procedure, è consigliabile farlo prima di distribuire Skype for Business Server.
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832246"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="73163-105">Procedure consigliate per l'infrastruttura di base in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="73163-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="73163-106">È probabile che siano già state intraprese azioni per progettare la tolleranza di errore nel sistema, ad esempio garantendo la ridondanza hardware, prendendo precauzioni in caso di interruzioni dell'alimentazione, installando con regolarità gli aggiornamenti antivirus e della sicurezza e monitorando l'attività dei server.</span><span class="sxs-lookup"><span data-stu-id="73163-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="73163-107">Queste procedure non sono utili solo per l'infrastruttura di Skype for Business Server, ma anche per l'intera rete.</span><span class="sxs-lookup"><span data-stu-id="73163-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="73163-108">Se non sono state implementate queste procedure, è consigliabile farlo prima di distribuire Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="73163-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="73163-109">Per proteggere i server della distribuzione di Skype for Business Server da un danno accidentale o intenzionale che potrebbe causare tempi di inattività, prendere le seguenti precauzioni:</span><span class="sxs-lookup"><span data-stu-id="73163-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="73163-110">Installare con regolarità gli aggiornamenti della sicurezza nei server.</span><span class="sxs-lookup"><span data-stu-id="73163-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="73163-111">Sottoscrivendo il servizio Microsoft Security Notification Service, è possibile ricevere una notifica immediata ogni volta che vengono pubblicati bollettini sulla sicurezza per i prodotti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="73163-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="73163-112">Per effettuare la sottoscrizione, visitare il [sito Web Microsoft Technical Security Notifications](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span><span class="sxs-lookup"><span data-stu-id="73163-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="73163-113">Verificare che i diritti di accesso siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="73163-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="73163-p104">Posizionare i server in un ambiente fisico con accesso consentito soltanto a personale autorizzato. Verificare che in tutti i server sia installato il software antivirus appropriato. Mantenere il software aggiornato con i file delle impronte digitali dei virus più recenti. Utilizzare la funzionalità di aggiornamento automatico dell'applicazione antivirus per mantenere costantemente aggiornate le impronte digitali dei virus.</span><span class="sxs-lookup"><span data-stu-id="73163-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="73163-118">Si consiglia di disabilitare i servizi del sistema operativo Windows Server che non sono necessari nei computer in cui si installa Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="73163-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="73163-119">Crittografare i sistemi operativi e le unità disco in cui sono archiviati i dati con un sistema di crittografia dell'intero volume, a meno che non sia possibile garantire il controllo completo e costante dei server, l'isolamento fisico totale e la rimozione delle autorizzazioni appropriata e sicura per le unità disco sostituite o guaste.</span><span class="sxs-lookup"><span data-stu-id="73163-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="73163-120">Disabilitare tutte le porte DMA (Direct Memory Access) esterne del server, a meno che non sia possibile garantire un controllo rigoroso dell'accesso fisico ai server.</span><span class="sxs-lookup"><span data-stu-id="73163-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="73163-121">Gli attacchi basati su DMA, che possono essere eseguiti piuttosto facilmente, rendono vulnerabili le informazioni riservate, ad esempio le chiavi di crittografia private.</span><span class="sxs-lookup"><span data-stu-id="73163-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

