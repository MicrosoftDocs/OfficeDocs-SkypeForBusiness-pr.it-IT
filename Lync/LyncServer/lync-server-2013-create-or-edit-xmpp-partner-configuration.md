---
title: 'Lync Server 2013: creare o modificare la configurazione del partner XMPP'
description: 'Lync Server 2013: creare o modificare la configurazione del partner XMPP.'
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
ms.openlocfilehash: 19289df1920287984f104bb1bdfa214d6f83f5cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553872"
---
# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>Creare o modificare la configurazione del partner XMPP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-09-03_

Microsoft Lync Server 2013 integra un proxy XMPP (Extensible Messaging and Presence Protocol) nel server perimetrale e un gateway XMPP nel front end server o nel pool Front end. Per consentire connessioni da altre distribuzioni XMPP, è necessario configurare XMPP nel pannello di controllo di Lync Server. Le impostazioni devono essere configurate sulla base del dominio XMPP. Per creare una nuova associazione di partner, procedere come segue:

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>Per creare un nuovo partner federato o modificare una configurazione esistente

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi su **Partner federati XMPP**.

4.  Per creare una nuova configurazione, fare clic su **Nuovo**

5.  Per modificare una configurazione esistente, selezionarla e fare clic su **Modifica**

6.  Per creare o modificare le configurazioni per i **Partner federati XMPP**, è necessario definire le impostazioni seguenti:

7.  **Dominio primario** (obbligatorio). Il dominio primario è il dominio di base del partner XMPP. Ad esempio, è necessario immettere **fabrikam.com** per il nome di dominio del partner XMPP. Questa voce è obbligatoria.

8.  **Descrizione**. La descrizione è costituita da note o altre informazioni di identificazione di questa specifica configurazione. Questa voce è facoltativa.

9.  **Domini aggiuntivi**. I domini aggiuntivi sono domini che fanno parte del dominio del partner XMPP che devono essere inclusi come parte delle comunicazioni XMPP consentite. Se ad esempio il dominio primario è **fabrikam.com**, si dovrebbero elencare tutti gli altri domini al di sotto di fabrikam.com con cui si comunicherà mediante il protocollo XMPP. Ad esempio, si potrebbe immettere **corp.fabrikam.com** e **it.fabrikam.com** per i domini XMPP Corporate e Information Technologies sotto il dominio XMPP principale di fabrikam.com.

10. **Tipo di partner**. Il **Tipo di partner** è un'impostazione obbligatoria che prevede la possibilità di scegliere tra tre opzioni di un menu a discesa. È necessario scegliere una delle opzioni seguenti per descrivere e specificare i contatti che si possono aggiungere. È possibile selezionare le opzioni seguenti:
    
      - **Federata**. Un tipo di partner **federato** è una connessione attendibile tra una distribuzione di partner di Lync Server o Office Communications Server 2007 R2.
    
      - **Pubblico verificato**. Un partner **verificato pubblico** è quando i contatti che fanno parte di una distribuzione verificata dal provider possono essere aggiunti all'elenco di contatti dell'utente. Gli inviti possono essere inviati dall'utente Lync o l'utente di Lync può accettare gli inviti dal contatto del partner.
    
      - **Pubblico non verificato**. Una relazione **pubblica non verificata** implica che non vi siano stati stabiliti e verificabili tra le due distribuzioni. Un utente di Lync deve invitare il contatto non verificato per il contatto per poter aggiungere l'utente Lync all'elenco dei contatti. Ad esempio, Google GTalk non è un servizio di verifica XMPP pubblico che si riferisce a Lync Server. Un utente di GTalk non sarà in grado di aggiungere l'utente Lync come contatto, a meno che non sia presente un invito esplicito inviato dall'utente Lync.

11. Note sulla negoziazione dei flussi e sui metodi di sicurezza TLS (Transport Layer Security) e SASL (Software Authentication and Security Layer):
    
    **XMPP Standards Foundation** (XSF) e **Internet Engineering Task Force** (IETF) definiscono un insieme di regole e standard per l'uso e la gestione dei certificati client TLS, dei certificati server TLS e del meccanismo SASL. L'utilizzo di TLS e SASL è la procedura richiesta per proteggere il flusso XMPP. Nella sintesi del documento **XEP-0178** gli standard XMPP specificano un flusso di protocollo consigliato per l'uso del meccanismo SASL EXTERNAL con i certificati PKIX, soprattutto nei casi in cui un servizio XMPP indica che è necessaria la negoziazione TLS. PKIX, come indicato nella documentazione relativa a XSF, fa riferimento all'infrastruttura a chiave pubblica, nota anche come PKI.
    
    Vedere il documento XSF XEP-0178 per altri dettagli sui requisiti del protocollo XMPP. Per informazioni dettagliate, vedere "XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates". <http://xmpp.org/extensions/xep-0178.html>
    
    Fare riferimento al documento IETF "protocollo XMPP (Extensible Messaging and Presence Protocol): Core", sezione 5,0, negoziazione STARTTLS <https://tools.ietf.org/html/rfc6120> .
    
      - **Negoziazione TLS**. Consente di definire le regole di negoziazione TLS. Un servizio XMPP può richiedere la negoziazione TLS, può definirla come facoltativa oppure l'utente può specificare che la negoziazione TLS non è supportata. Se si seleziona Facoltativa, l'eventuale obbligatorietà della negoziazione viene decisa dal servizio XMPP. Per visualizzare tutte le impostazioni e i dettagli possibili per la negoziazione SASL, TLS e richiamata, incluse le configurazioni degli errori non valide e note, vedere [impostazioni di negoziazione per i partner federati XMPP in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Obbligatorio**. Il servizio XMPP richiede la negoziazione TLS.
        
          - <span></span>  
            **Facoltativo**. Il servizio XMPP indica se esiste l'obbligo di negoziare con TLS.
        
          - <span></span>  
            **Non supportato**. Il servizio XMPP non supporta la negoziazione TLS.
    
      - **Negoziazione SASL**. Consente di definire le regole di negoziazione SASL. Un servizio XMPP può richiedere la negoziazione SASL, può definirla come facoltativa oppure l'utente può specificare che la negoziazione SASL non è supportata. Se si sceglie di renderlo facoltativo, sarà il servizio XMPP a stabilire se rendere obbligatorio il protocollo per consentire la negoziazione.
        
        <div>
        

        > [!WARNING]  
        > In SASL è richiesto TLS. Per poter usare SASL, è necessario specificare se TLS deve essere obbligatorio o facoltativo. Qualsiasi configurazione che definisca SASL come obbligatorio o facoltativo deve prevedere il supporto di TLS. Se non si specifica se TLS deve essere obbligatorio o facoltativo e si fa clic su <STRONG>Commit</STRONG> per salvare le modifiche, viene visualizzato un avviso che segnala che SASL deve prevedere il supporto di TLS e che le modifiche non verranno salvate. Per risolvere l'errore, impostare TLS su <STRONG>Richiesto</STRONG> o su <STRONG>Facoltativo</STRONG>. Se l'uso di SASL è facoltativo e il supporto della negoziazione TLS non è possibile, è necessario impostare la negoziazione SASL su <STRONG>Non supportato</STRONG>. Verificare con il servizio XMPP quali sono flussi di negoziazione appropriati per TLS e SASL per evitare che il servizio venga interrotto.

        
        </div>
        
          - <span></span>  
            **Obbligatorio**. Il servizio XMPP richiede la negoziazione SASL.
        
          - <span></span>  
            **Facoltativo**. Il servizio XMPP indica se esiste l'obbligo di negoziare con SASL.
        
          - <span></span>  
            **Non supportato**. Il servizio XMPP non supporta la negoziazione SASL.
    
      - **Negoziazione richiamata**. La negoziazione di richiamata è definita dal XSF nel documento **XEP-220: server richiamata** <http://xmpp.org/extensions/xep-0220.html> . Il processo del server richiamata utilizza il DNS (Domain Name System) e un server autorevole per verificare che la richiesta provenisse da un partner XMPP valido. A tale scopo, il server di origine crea un messaggio di un tipo specifico con una chiave richiamata generata e cerca il server di ricezione in DNS. Il server di origine invia la chiave in un flusso XML alla ricerca DNS risultante, presumibilmente il server di ricezione. Al ricevimento della chiave tramite il flusso XML, il server di ricezione non risponde al server di origine, ma invia la chiave a un server autorevole noto. Il server autorevole verifica che la chiave sia valida o non valida. Se non è valido, il server di ricezione non risponde al server di origine. Se la chiave è valida, il server di ricezione informa il server di origine che l'identità e la chiave sono valide e che la conversazione può iniziare.
        
        Sono disponibili due stati validi per la negoziazione di tipo **Dialback**:
        
          - <span></span>  
            **Vero**. Il server XMPP è configurato per usare Dialback Negotiation nel caso in cui si riceva una richiesta da un server di origine
        
          - <span></span>  
            Valore **false**. Il server XMPP non è configurato per l'utilizzo di Dialback Negotiation e, se si ricevesse una richiesta da un server di origine, verrebbe ignorata

</div>

</div>

<span> </span>

</div>

</div>

</div>

