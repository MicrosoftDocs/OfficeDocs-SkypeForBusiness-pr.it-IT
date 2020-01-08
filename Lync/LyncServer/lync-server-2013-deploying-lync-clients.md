---
title: 'Lync Server 2013: distribuzione di client Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbbecc50ed88ac9b3237277ba1c991f8c1fcba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>Distribuzione di client Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Lync 2013 introduce un approccio diverso alla distribuzione del client. In partenza dalle versioni precedenti, Lync 2013 non ha più il proprio programma di installazione. Lync è invece incluso nel programma di installazione di Office 2013. Per distribuire Lync 2013 agli utenti, è possibile usare i metodi di installazione e gli strumenti di personalizzazione di Office 2013.

  - **Office 2013 Windows Installer** è un pacchetto di installazione basato su Windows Installer costituito da più file MSI. Un pacchetto MSI di base indipendente dalla lingua viene combinato con uno o più pacchetti specifici della lingua per creare un prodotto completo. La configurazione assembla i singoli pacchetti ed esegue le attività di personalizzazione e manutenzione durante e dopo l'installazione di Office nei computer degli utenti. Negli argomenti di questa sezione viene descritto come usare e personalizzare Office 2013 Windows Installer per distribuire Lync 2013.

  - **Office 2013** a portata di clic è un programma di installazione che esegue il flusso di file di installazione di Office per l'utente dal portale di Microsoft Office 365. Gli amministratori possono personalizzare l'installazione usando lo strumento di distribuzione di Office per l'esecuzione a portata di clic. Poiché Office 2013 a portata di clic viene usato principalmente nell'ambiente Microsoft Office 365, questo metodo di installazione non viene descritto in dettaglio in questa sezione. Informazioni dettagliate sull'uso e la personalizzazione dell'installazione a portata di clic sono disponibili nella documentazione di Office 2013 Resource Kit. Gli amministratori possono anche scaricare i file di origine del programma e della lingua di Office 2013 a portata di clic in una posizione locale, utile quando si vuole minimizzare la richiesta della rete o impedire agli utenti di installare il software da Internet a causa di requisiti di sicurezza aziendale.

Gli argomenti di questa sezione sono incentrati su come distribuire i client tramite il programma di installazione di Office 2013 basato su MSI. Il riferimento principale dovrebbe essere la documentazione di Office 2013 Resource Kit, che descrive in dettaglio come preparare l'infrastruttura, personalizzare la configurazione e distribuire Office 2013. Tuttavia, è consigliabile usare la documentazione di Office in combinazione con gli argomenti in questa sezione, che evidenziano considerazioni sulla distribuzione specifiche di Lync 2013.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Il componente aggiuntivo riunione online per Lync 2013, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, viene installato automaticamente con Lync 2013.</P>
> <LI>
> <P>Il programma di installazione di Office 2013 non disinstalla versioni precedenti di Lync o Office Communicator. Il client Lync 2013 installa affiancato ad altri client Lync o Office Communicator</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Personalizzazione dell'installazione client in Lync Server 2013](lync-server-2013-customizing-client-installation.md)

  - [Personalizzazione del comportamento di Lync e dell'interfaccia utente in Lync Server 2013](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Personalizzazione del componente aggiuntivo riunione online in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Configurazione della pagina di partecipazione alle riunioni in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Configurazione di versioni client supportate in Lync Server 2013](lync-server-2013-configuring-supported-client-versions.md)

  - [Configurazione della modalità di privacy della presenza avanzata in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

