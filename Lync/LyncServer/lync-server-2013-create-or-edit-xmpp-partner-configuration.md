---
title: 'Lync Server 2013: Creare o modificare la configurazione dei partner XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488665bca5cd2ad1b4d2d91a3c85a6a1ddaa3916
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Creare o modificare la configurazione dei partner XMPP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-09-03_

Microsoft Lync Server 2013 integra un proxy XMPP (Extensible Messaging and Presence Protocol) nell'Edge Server e un gateway XMPP nel server front-end o nel pool Front-end. Per consentire connessioni da altre distribuzioni XMPP, è necessario configurare XMPP nel pannello di controllo di Lync Server. Le impostazioni vengono configurate in base al dominio XMPP. Per creare una nuova associazione partner, eseguire le operazioni seguenti:

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>Per creare un nuovo partner federato o modificare una configurazione esistente

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi fare clic su **partner federativi XMPP**.

4.  Per creare una nuova configurazione, fare clic su **nuovo**

5.  Per modificare una configurazione esistente, selezionare la configurazione e fare clic su **modifica**

6.  Per creare o modificare le configurazioni per i **partner federati XMPP**, è possibile definire le impostazioni seguenti:

7.  **Dominio principale** (obbligatorio). Il dominio principale è il dominio di base del partner XMPP. Ad esempio, immetti **Fabrikam.com** per il nome di dominio partner XMPP. Questa è una voce obbligatoria.

8.  **Descrizione**. La descrizione riguarda le note o altre informazioni di identificazione per questa particolare configurazione. Questa voce è facoltativa.

9.  **Altri domini**. I domini aggiuntivi sono domini che fanno parte del dominio del partner XMPP che deve essere incluso come parte della comunicazione XMPP consentita. Ad esempio, se il dominio principale è **Fabrikam.com**, devi elencare tutti gli altri domini in Fabrikam.com con cui comunicherai per mezzo di XMPP. Ad esempio, è possibile immettere **Corp.fabrikam.com** e **it.fabrikam.com** per il dominio XMPP aziendale e il dominio XMPP delle tecnologie informative sotto il dominio XMPP principale di Fabrikam.

10. **Tipo di partner**. Il **tipo di partner** è un'impostazione obbligatoria e offre una selezione di tre opzioni in un menu a discesa. È necessario scegliere una delle opzioni seguenti per descrivere e applicare i contatti che è possibile aggiungere. È possibile selezionare una delle opzioni seguenti:
    
      - **Federati**. Un tipo di partner **federato** è una connessione attendibile tra una distribuzione di partner di Lync Server o Office Communications Server 2007 R2.
    
      - **Pubblico verificato**. Un partner **verificato pubblico** si trova quando i contatti che fanno parte di una distribuzione verificata dal provider possono essere aggiunti all'elenco di contatti dell'utente. Gli inviti possono essere inviati dall'utente di Lync o l'utente di Lync può accettare gli inviti dal contatto del partner.
    
      - **Pubblico non verificato**. Una relazione **pubblica non verificata** implica che non ci sia stato stabilito e verificabile tra le due distribuzioni. Un utente di Lync deve invitare il contatto non verificato per il contatto per poter aggiungere l'utente di Lync all'elenco contatti. Ad esempio, Google GTalk non è un servizio pubblico verificato per l'XMPP quando si riferisce a Lync Server. Un utente di GTalk non sarà in grado di aggiungere l'utente di Lync come contatto, a meno che non sia presente un invito esplicito inviato dall'utente di Lync.

11. Note sulla negoziazione Stream e i metodi di sicurezza Transport Layer Security (TLS) e software Authentication and Security Layer (SASL):
    
    La rete di **standard XMPP** (xsf) e la **Internet Engineering Task Force** (IETF) definiscono un set di regole e standard per l'uso e la gestione dei certificati client TLS, dei certificati server TLS e del meccanismo SASL. L'uso di TLS e SASL è il processo necessario per proteggere il flusso XMPP. Dal documento di standard XMPP **XEP-0178**"specifica un flusso di protocollo consigliato per l'uso del meccanismo esterno SASL con certificati PKIX, in particolare quando un servizio XMPP indica che TLS è obbligatorio da negoziare". PKIX, come indicato nella documentazione XSF, fa riferimento all'infrastruttura a chiave pubblica, nota anche come PKI.
    
    Per altre informazioni sui requisiti XMPP, vedere il documento XSF XEP-0178. Per informazioni dettagliate, vedere "XEP-0178: procedure consigliate per l'uso di SASL EXTERNAL with Certificates". <http://xmpp.org/extensions/xep-0178.html>
    
    Fare riferimento al documento IETF "Extensible Messaging and Presence Protocol (XMPP): Core", sezione 5,0, negoziazione <http://tools.ietf.org/html/rfc6120>STARTTLS.
    
      - **Negoziazione TLS**. Definisce le regole di negoziazione TLS. Un servizio XMPP può richiedere TLS, può rendere facoltativo TLS oppure definire che TLS non è supportato. La scelta facoltativa lascia il requisito fino al servizio XMPP per una decisione obbligatorio-negoziare. Per visualizzare tutte le impostazioni e i dettagli possibili per la negoziazione SASL, TLS e richiamata, incluse le configurazioni di errore non valide e note, vedere [impostazioni di negoziazione per partner federati XMPP in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Obbligatorio**. Il servizio XMPP richiede la negoziazione TLS.
        
          - <span></span>  
            **Facoltativo**. Il servizio XMPP indica che TLS è obbligatorio da negoziare.
        
          - <span></span>  
            **Non supportato**. Il servizio XMPP non supporta TLS.
    
      - **Negoziazione SASL**. Definisce le regole di negoziazione SASL. Un servizio XMPP può richiedere SASL, può rendere SASL facoltativo o Definisci che SASL non è supportato. La scelta facoltativa lascia il requisito fino al servizio XMPP partner per una decisione obbligatorio-to-negotiate.
        
        <div>
        

        > [!WARNING]  
        > SASL richiede TLS. Per usare SASL, TLS deve essere obbligatorio o facoltativo. Qualsiasi configurazione che definisce SASL come obbligatorio o facoltativo deve avere il supporto TLS. Quando si fa clic su <STRONG>conferma</STRONG> per salvare le modifiche, se non è stato impostato TLS su obbligatorio o facoltativo, viene avvisato che SASL deve avere il supporto TLS e che le modifiche non vengono salvate. Per risolvere l'errore, impostare TLS su <STRONG>obbligatorio</STRONG> o <STRONG>facoltativo</STRONG>. Se l'uso di SASL è facoltativo e non è possibile il supporto delle negoziazioni TLS, è necessario impostare la negoziazione SASL su <STRONG>non supportata</STRONG>. Verificare con il servizio XMPP che cosa devono essere i flussi di negoziazione appropriati per TLS e SASL o l'interruzione del servizio.

        
        </div>
        
          - <span></span>  
            **Obbligatorio**. Il servizio XMPP richiede la negoziazione SASL.
        
          - <span></span>  
            **Facoltativo**. Il servizio XMPP indica che SASL è obbligatorio-negoziare.
        
          - <span></span>  
            **Non supportato**. Il servizio XMPP non supporta SASL.
    
      - **Negoziazione richiamata**. La negoziazione richiamata è definita dall'elemento XSF nel documento **XEP-220: server richiamata** <http://xmpp.org/extensions/xep-0220.html>. Il processo server richiamata USA Domain Name System (DNS) e un server autorevole per verificare che la richiesta provenisse da un partner XMPP valido. A questo scopo, il server di origine crea un messaggio di un tipo specifico con una chiave richiamata generata e cerca il server di ricezione nel DNS. Il server di origine invia la chiave in un flusso XML alla ricerca DNS risultante, presumibilmente il server di ricezione. Al ricevimento della chiave sul flusso XML, il server di ricezione non risponde al server di origine, ma invia la chiave a un server autorevole noto. Il server autorevole verifica che la chiave sia valida o non valida. Se non è valido, il server di ricezione non risponde al server di origine. Se la chiave è valida, il server di ricezione informa il server di origine che l'identità e la chiave sono valide e che la conversazione può iniziare.
        
        Esistono due stati validi per la **negoziazione richiamata**:
        
          - <span></span>  
            **Vero**. Il server XMPP è configurato per l'uso della negoziazione richiamata se una richiesta deve essere ricevuta da un server di origine
        
          - <span></span>  
            **False**. Il server XMPP non è configurato per l'uso della negoziazione richiamata e se una richiesta deve essere ricevuta da un server di origine, verrà ignorata

</div>

</div>

<span> </span>

</div>

</div>

</div>

