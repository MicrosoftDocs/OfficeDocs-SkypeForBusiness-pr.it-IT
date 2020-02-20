---
title: "Lync Server 2013: protezione dei dati per l'abbinamento del pool Front End"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26759c982723fd656ac3456aad630bc695a7343e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Sicurezza dei dati per l'abbinamento del pool Front end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-10-07_

Il servizio di backup è un meccanismo di replica dei dati introdotto in Lync Server 2013 che trasferisce i dati degli utenti e il contenuto delle conferenze tra due pool Front End abbinati in modo continuo tra due centri dati per scopi di ripristino di emergenza. I dati utente contengono gli URI SIP nonché gli elenchi contatti e le impostazioni. Il contenuto delle conferenze include i caricamenti di Microsoft PowerPoint 2010, nonché le lavagne utilizzate nelle conferenze. Dal pool di origine, i dati utente e i contenuti delle conferenze vengono esportati dall'archiviazione locale, compressi e trasferiti nel pool di destinazione, dove vengono decompressi e importati nell'archiviazione locale. Il Servizio di backup presume che i collegamenti di comunicazione tra i due data center si trovino all'interno di una rete aziendale protetta da Internet. I dati trasferiti tra i due data center non vengono crittografati, né è previsto l'incapsulamento nativo all'interno di un protocollo di sicurezza, quale HTTPS. Pertanto resta possibile un attacco man-in-the-middle compiuto da personale interno alla rete aziendale.

<div>

## <a name="evaluating-security-risks"></a>Valutazione dei rischi per la sicurezza

Qualsiasi organizzazione che distribuisce Lync Server 2013 su più data center e utilizza la funzionalità di ripristino di emergenza deve garantire che il traffico tra i Data Center sia protetto dalla propria Intranet aziendale. Le aziende che intendono cautelarsi dal rischio di un attacco interno, devono proteggere i collegamenti di comunicazione tra i data center.

In genere, si suppone che i data center di un'azienda siano protetti nella Intranet aziendale. Molti altri tipi di dati aziendali riservati vengono trasferiti tra questi data center. L'infrastruttura IT dell'azienda è esposta a seri pericoli se i collegamenti tra data center non sono protetti.

Sebbene in un'azienda esista il pericolo di attacchi man-in-the-middle, è relativamente contenuto se paragonato al rischio di esporre il traffico in Internet. In particolare, i dati utente esposti dal Servizio di backup (ad esempio gli URI SIP) sono generalmente disponibili a tutti gli utenti dell'azienda con altri mezzi, quali la Rubrica globale di Exchange o altri software di directory. Quando viene utilizzato il Servizio backup per copiare dati tra due pool abbinati, è pertanto necessario concentrarsi sulla protezione della WAN tra i due data center.

</div>

<div>

## <a name="mitigating-security-risks"></a>Contenere i rischi per la sicurezza

Esistono diversi modi per migliorare la protezione della sicurezza per il traffico dei servizi di backup, che varia da limitare l'accesso ai Data Center per garantire il trasporto WAN tra i due data center. Nella maggior parte dei casi, le aziende che distribuiscono Lync Server 2013 potrebbe già disporre dell'infrastruttura di sicurezza necessaria. Per le aziende alla ricerca di linee guida, Microsoft fornisce una soluzione come esempio di come creare un'infrastruttura IT sicura. Tuttavia, ciò non implica che sia l'unica soluzione, né implica che sia la soluzione preferita per Lync Server. Si consiglia ai clienti aziendali di scegliere la soluzione adatta alle proprie esigenze specifiche, in base all'infrastruttura e ai requisiti di sicurezza IT. Nell'esempio di soluzione Microsoft vengono impiegati IPSec e criteri di gruppo per l'isolamento del server e del dominio. Per informazioni dettagliate, [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544)vedere. Per domande e commenti, contattare secwish@microsoft.com.

Un'altra possibile soluzione consiste nell'utilizzare IPSec solo per garantire la protezione dei dati inviati dal servizio di backup stesso. Se si sceglie questo metodo, è necessario configurare le regole IPSec per il protocollo SMB per i server seguenti, in cui il pool A e il pool B sono due pool Front End abbinati.

  - Il servizio SMB (TCP/445) di ogni front end server del pool A nell'archivio file utilizzato dal pool B.

  - Il servizio SMB (TCP/445) da ogni Front End Server nel pool B all'archivio file utilizzato dal pool A.

<div>


> [!WARNING]  
> IPsec non è destinato a essere sostituito per la sicurezza a livello di applicazione, ad esempio SSL/TLS. Un vantaggio dell'utilizzo di IPsec è che può garantire la sicurezza del traffico di rete per le applicazioni esistenti senza dover cambiare. Le aziende che desiderano garantire solo il trasporto tra i due data center devono consultare i rispettivi fornitori di hardware di rete in merito alle modalità di configurazione delle connessioni WAN sicure tramite l'equipaggiamento del fornitore.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

