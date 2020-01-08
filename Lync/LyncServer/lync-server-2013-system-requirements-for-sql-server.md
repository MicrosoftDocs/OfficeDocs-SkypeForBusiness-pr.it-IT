---
title: 'Lync Server 2013: Requisiti di sistema per SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48184904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8e8bb923fd10d505eb9e1b02b0b0ee31612d40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="8b43b-102">Requisiti di sistema per SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b43b-102">System requirements for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b43b-103">_**Argomento Ultima modifica:** 2013-10-25_</span><span class="sxs-lookup"><span data-stu-id="8b43b-103">_**Topic Last Modified:** 2013-10-25_</span></span>

<span data-ttu-id="8b43b-104">Prima di distribuire il server Enterprise Edition, installare Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 in un computer dedicato che soddisfi i requisiti hardware.</span><span class="sxs-lookup"><span data-stu-id="8b43b-104">Before you deploy Enterprise Edition server, install Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 on a dedicated computer that meets the hardware requirements.</span></span> <span data-ttu-id="8b43b-105">Per informazioni dettagliate sui requisiti hardware, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="8b43b-105">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="8b43b-106">Per informazioni dettagliate sui requisiti software, vedere [supporto software per database in Lync Server 2013](lync-server-2013-database-software-support.md) nella documentazione relativa al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="8b43b-106">For details about software requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="8b43b-107">Per informazioni sulle autorizzazioni necessarie per la distribuzione, vedere [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8b43b-107">For information about the permissions necessary for deployment, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<span data-ttu-id="8b43b-108">Prima di creare il pool Front-End, è necessario configurare anche Windows Firewall per consentire l'accesso di Lync Server 2013 a SQL Server su porte specifiche definendo le porte del server tramite Gestione configurazione SQL Server e aprendo le porte in Windows Firewall con Sicurezza avanzata.</span><span class="sxs-lookup"><span data-stu-id="8b43b-108">Before you create the Front End pool, you must also configure Windows Firewall to allow Lync Server 2013 access to SQL Server over specific ports by defining ports for the server using SQL Server Configuration Manager and opening ports in Windows Firewall with Advanced Security.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

