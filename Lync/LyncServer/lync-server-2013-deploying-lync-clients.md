---
title: 'Lync Server 2013: distribuzione di client Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fa0bae9909015ca8cefe52cc09dabbe7a4419b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>Distribuzione di client Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Lync 2013 introduce un approccio diverso alla distribuzione del client. In una partenza dalle versioni precedenti, Lync 2013 non ha più un proprio programma di installazione. Lync, invece, è incluso nel programma di installazione di Office 2013. Per distribuire Lync 2013 agli utenti, è possibile utilizzare i metodi di installazione e gli strumenti di personalizzazione di Office 2013.

  - **Office 2013 Windows Installer** è un pacchetto di installazione basato su Windows Installer costituito da più file MSI. La creazione di un prodotto completo si basa sulla combinazione di un pacchetto MSI principale indipendente dalla lingua con uno o più pacchetti specifici della lingua. I singoli pacchetti vengono assemblati durante l'installazione mentre le attività di personalizzazione e manutenzione vengono eseguite durante e dopo l'installazione di Office nei computer degli utenti. Negli argomenti di questa sezione viene descritto come utilizzare e personalizzare il programma di installazione di Windows di Office 2013 per la distribuzione di Lync 2013.

  - **Office 2013 a** portata di clic è un programma di installazione che consente di eseguire il flusso dei file di installazione di Office all'utente dal portale di Microsoft Office 365. Gli amministratori possono personalizzare l'installazione utilizzando lo strumento di distribuzione di Office per la funzione a portata di clic. Poiché la funzione a portata di clic di Office 2013 viene utilizzata principalmente nell'ambiente Microsoft Office 365, questo metodo di installazione non viene descritto in dettaglio in questa sezione. Per informazioni dettagliate sull'utilizzo e la personalizzazione dell'installazione a portata di clic, vedere la documentazione di Office 2013 Resource Kit. Gli amministratori possono anche scaricare il programma di Office 2013 a portata di clic e i file di origine della lingua in una posizione locale, che è utile quando si desidera ridurre al minimo la richiesta sulla rete o impedire agli utenti di installare il software da Internet a causa di requisiti di sicurezza aziendale.

Negli argomenti di questa sezione vengono illustrate le modalità di distribuzione dei client tramite il programma di installazione di Office 2013 basato su MSI. Il riferimento primario dovrebbe essere la documentazione di Office 2013 Resource Kit, in cui vengono descritti in dettaglio la modalità di preparazione dell'infrastruttura, la personalizzazione dell'installazione e la distribuzione di Office 2013. Tuttavia, è consigliabile utilizzare la documentazione di Office in combinazione con gli argomenti di questa sezione, in cui vengono indicate le considerazioni relative alla distribuzione specifiche di Lync 2013.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Il componente aggiuntivo per riunioni online per Lync 2013, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, viene installato automaticamente con Lync 2013.</P>
> <LI>
> <P>Il programma di installazione di Office 2013 non disinstalla le versioni precedenti di Lync o Office Communicator. Il client Lync 2013 installa affiancati con altri client Lync o Office Communicator</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Personalizzazione dell'installazione client in Lync Server 2013](lync-server-2013-customizing-client-installation.md)

  - [Personalizzazione del comportamento di Lync e dell'interfaccia utente in Lync Server 2013](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Personalizzazione del componente aggiuntivo per riunioni online in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Configurazione della pagina di partecipazione alle riunioni in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Configurazione delle versioni client supportate in Lync Server 2013](lync-server-2013-configuring-supported-client-versions.md)

  - [Configurazione della modalità privacy della presenza avanzata in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

