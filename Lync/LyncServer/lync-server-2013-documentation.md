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
ms.openlocfilehash: 6eaeb06f1d9144d0c6f28984d509b3777673e10f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="46a3c-102">Documentazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46a3c-102">Documentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46a3c-103">_**Argomento Ultima modifica:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="46a3c-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="46a3c-104">Il modello MOF è costituito da numerose funzioni di gestione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="46a3c-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="46a3c-105">La documentazione su come e quando eseguire le attività può essere condivisa con i membri dello stesso team o con altri team.</span><span class="sxs-lookup"><span data-stu-id="46a3c-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="46a3c-106">Il metodo di archiviazione e condivisione della documentazione può variare in base al tipo di funzione.</span><span class="sxs-lookup"><span data-stu-id="46a3c-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="46a3c-107">Le procedure per l'amministrazione di sistema, ad esempio, possono essere archiviate come documenti di Word, in quanto probabilmente verranno stampate e riportate a un riferimento frequente.</span><span class="sxs-lookup"><span data-stu-id="46a3c-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="46a3c-108">Le informazioni di gestione della configurazione possono essere generate e archiviate automaticamente in un database per facilitare la ricerca e l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="46a3c-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="46a3c-109">Una certa documentazione può essere sensibile e deve essere limitata.</span><span class="sxs-lookup"><span data-stu-id="46a3c-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="46a3c-110">Sistemi di gestione dei documenti</span><span class="sxs-lookup"><span data-stu-id="46a3c-110">Document management systems</span></span>

<span data-ttu-id="46a3c-111">Un sistema di gestione della documentazione funge da repository centrale per i documenti e consente di verificare che sia disponibile solo l'ultima versione di un documento.</span><span class="sxs-lookup"><span data-stu-id="46a3c-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="46a3c-112">È anche possibile considerare l'archiviazione della versione precedente del documento come riferimento.</span><span class="sxs-lookup"><span data-stu-id="46a3c-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="46a3c-113">Lync Server offre funzionalità adatte per questa attività.</span><span class="sxs-lookup"><span data-stu-id="46a3c-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="46a3c-114">Database</span><span class="sxs-lookup"><span data-stu-id="46a3c-114">Databases</span></span>

<span data-ttu-id="46a3c-115">Sono stati discussi diversi strumenti e funzioni di gestione adatti all'uso dei database.</span><span class="sxs-lookup"><span data-stu-id="46a3c-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="46a3c-116">Il processo di gestione della configurazione rischia di usare processi automatizzati che memorizzano grandi quantità di dati che richiedono l'indicizzazione e la ricerca.</span><span class="sxs-lookup"><span data-stu-id="46a3c-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="46a3c-117">Il personale di supporto può cercare un database di problemi e risoluzioni precedenti quando si risolvono nuovi problemi.</span><span class="sxs-lookup"><span data-stu-id="46a3c-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="46a3c-118">È probabile che vengano usati database diversi per scopi diversi.</span><span class="sxs-lookup"><span data-stu-id="46a3c-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="46a3c-119">Decidere se questi database devono essere collegati o combinati.</span><span class="sxs-lookup"><span data-stu-id="46a3c-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="46a3c-120">Ad esempio, se il servizio di assistenza identifica diversi problemi con un tema comune (ad esempio il nuovo software che causa un problema con una specifica scheda di rete), il personale di supporto può eseguire una query nel database di configurazione per prevedere il numero di computer che potrebbero essere interessati.</span><span class="sxs-lookup"><span data-stu-id="46a3c-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

