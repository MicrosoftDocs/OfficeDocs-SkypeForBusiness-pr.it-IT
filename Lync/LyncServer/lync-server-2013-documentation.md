---
title: 'Lync Server 2013: documentazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2705cd5d2dd473fa98ae44398b2d1eb0c812c9f8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="e1bd4-102">Documentazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1bd4-102">Documentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1bd4-103">_**Ultimo argomento modificato:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="e1bd4-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="e1bd4-104">Il modello MOF è costituito da numerose funzioni di gestione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="e1bd4-105">La documentazione su come e quando eseguire le attività può essere condivisa con i membri dello stesso team o con altri team.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="e1bd4-106">Il metodo di archiviazione e condivisione della documentazione può variare in base al tipo di funzione.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="e1bd4-107">Ad esempio, le procedure per l'amministrazione del sistema possono essere archiviate come documenti di Word perché è probabile che vengano stampate e referenziate frequentemente.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="e1bd4-108">Le informazioni di gestione della configurazione possono essere generate e archiviate automaticamente in un database per semplificare la ricerca e l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="e1bd4-109">Alcuni documenti possono essere sensibili e devono essere limitati.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="e1bd4-110">Sistemi di gestione dei documenti</span><span class="sxs-lookup"><span data-stu-id="e1bd4-110">Document management systems</span></span>

<span data-ttu-id="e1bd4-111">Un sistema di gestione della documentazione funge da archivio centrale per i documenti e assicura che sia disponibile solo l'ultima revisione di un documento.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="e1bd4-112">È inoltre possibile valutare la possibilità di archiviare la versione precedente del documento come riferimento.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="e1bd4-113">Lync Server fornisce la funzionalità adatta a questa attività.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="e1bd4-114">Database</span><span class="sxs-lookup"><span data-stu-id="e1bd4-114">Databases</span></span>

<span data-ttu-id="e1bd4-115">Sono stati descritti diversi strumenti e funzioni di gestione che sono adatti all'utilizzo dei database.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="e1bd4-116">È probabile che il processo di gestione della configurazione utilizzi processi automatici che archiviano grandi quantità di dati che richiedono l'indicizzazione e la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="e1bd4-117">Il personale di supporto può eseguire ricerche in un database di problemi e risoluzioni precedenti durante la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="e1bd4-118">È probabile che vengano utilizzati database diversi per scopi diversi.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="e1bd4-119">Decidere se questi database devono essere collegati o combinati.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="e1bd4-120">Ad esempio, se il service desk identifica diversi problemi con un tema comune (ad esempio un nuovo software che causa un problema con una scheda di rete specifica), il personale di supporto può eseguire query sul database di configurazione per prevedere il numero di computer che potrebbero essere intaccati.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

