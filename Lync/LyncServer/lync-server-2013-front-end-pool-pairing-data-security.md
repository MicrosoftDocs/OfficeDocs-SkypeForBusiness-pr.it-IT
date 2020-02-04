---
title: "Lync Server 2013: sicurezza dei dati per l'abbinamento dei pool Front End"
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
ms.openlocfilehash: efe51da622107183d3dbf2897a9e2a708acd78dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Sicurezza dei dati per l'abbinamento dei pool Front End in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-10-07_

Il servizio di backup è un meccanismo di replica dei dati introdotto in Lync Server 2013 che trasferisce i dati degli utenti e il contenuto delle conferenze tra due pool di front end associati in due centri dati per scopi di ripristino di emergenza. I dati degli utenti contengono URI SIP degli utenti, nonché elenchi di contatti e impostazioni. Il contenuto della conferenza include gli upload di Microsoft PowerPoint 2010 e le lavagne usate nelle conferenze. Dal pool di origine, i dati utente e il contenuto della conferenza vengono esportati dall'archivio locale, compressi, trasferiti nel pool di destinazione, dove vengono decompressi e importati nello spazio di archiviazione locale. Il servizio di backup presuppone che il collegamento delle comunicazioni tra i due centri dati si trovi all'interno della rete aziendale protetta da Internet. Non crittografa i dati trasferiti tra i due centri dati, né è incapsulato nativamente in un protocollo sicuro, ad esempio HTTPS. Di conseguenza, è possibile l'attacco man-in-the-Middle da parte di personale interno della rete aziendale.

<div>

## <a name="evaluating-security-risks"></a>Valutazione dei rischi per la sicurezza

Qualsiasi organizzazione che distribuisce Lync Server 2013 in più centri dati e usa la funzionalità di ripristino di emergenza deve garantire che il traffico tra i dati sia protetto dalla propria Intranet aziendale. Le aziende che preoccupano la protezione dagli attacchi interni devono garantire i collegamenti di comunicazione tra i centri dati.

Il presupposto che i Data Center di un'azienda siano protetti dietro l'Intranet aziendale è standard. Ci sono molti altri tipi di dati sensibili aziendali trasferiti tra questi Data Center. L'infrastruttura IT dell'organizzazione ha un rischio grave se questi collegamenti al centro dati incrociati non sono protetti.

Mentre il rischio di attacchi man-in-the-Middle all'interno della rete aziendale esiste, è relativamente contenuto rispetto a esporre il traffico a Internet. In particolare, i dati utente esposti dal servizio di backup, ad esempio URI SIP, sono in genere disponibili per tutti i dipendenti della società tramite altri mezzi, ad esempio la Rubrica globale di Exchange o un altro software di directory. Lo stato attivo deve quindi essere la protezione della WAN tra i due centri dati quando viene usato il servizio di backup per copiare i dati tra i due pool associati.

</div>

<div>

## <a name="mitigating-security-risks"></a>Attenuazione dei rischi per la sicurezza

Esistono diversi modi per migliorare la protezione della sicurezza per il traffico dei servizi di backup, che va dalla restrizione dell'accesso ai Data Center per garantire il trasporto WAN tra i due centri dati. Nella maggior parte dei casi, le aziende che distribuiscono Lync Server 2013 potrebbero già disporre dell'infrastruttura di sicurezza necessaria. Per le aziende che cercano indicazioni, Microsoft offre una soluzione come esempio di creazione di un'infrastruttura IT sicura. Ciò non implica tuttavia che sia l'unica soluzione, né implichi che sia la soluzione preferita per Lync Server. È consigliabile che i clienti aziendali scelgano la soluzione più adatta alle proprie esigenze specifiche, in base all'infrastruttura e ai requisiti di sicurezza IT. L'esempio di soluzione Microsoft usa IPSec e criteri di gruppo per l'isolamento del server e del dominio. Per informazioni dettagliate, [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)vedere. Per domande e commenti, contattare secwish@microsoft.com.

Un'altra possibile soluzione consiste nell'usare IPSec solo per proteggere i dati inviati dal servizio di backup stesso. Se si sceglie questo metodo, è necessario configurare le regole IPSec per il protocollo SMB per i server seguenti, dove pool A e pool B sono due pool Front-End associati.

  - Servizio SMB (TCP/445) da ogni server front-end del pool a all'archivio di file usato dal pool B.

  - Il servizio SMB (TCP/445) di ogni server front-end nel pool B nell'archivio file usato dal pool A.

<div>


> [!WARNING]  
> IPsec non è concepito come sostituzione per la sicurezza a livello di applicazione, ad esempio SSL/TLS. Un vantaggio dell'uso di IPsec è che può assicurare la sicurezza del traffico di rete per le applicazioni esistenti senza doverle cambiare. Le aziende che vogliono garantire semplicemente il trasporto tra i due centri dati devono consultare i rispettivi fornitori di hardware per la rete in merito alle modalità di configurazione delle connessioni WAN sicure tramite l'equipaggiamento del fornitore.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

