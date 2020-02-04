---
title: 'Lync Server 2013: Configurare i certificati per il server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fccab201ee9ab16b0195bc2780c37ab85f0519e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Configurare i certificati per il server Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Quando si esegue la creazione guidata certificato, verificare di avere effettuato l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà usato. Per impostazione predefinita, una richiesta di certificato di Lync Server 2013 utilizzerà il modello di certificato del server Web. Se si usa un account che è un membro del gruppo RTCUniversalServerAdmins per richiedere un certificato con questo modello, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione necessarie per l'uso di tale modello.



</div>

Ogni amministratore richiede un certificato predefinito, un certificato interno Web e un certificato esterno Web. Per informazioni dettagliate sui requisiti dei certificati per gli amministratori, vedere [requisiti di certificato per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.

Usare la procedura seguente per configurare i certificati di Director. Ripetere la procedura per ogni amministratore. I passaggi di questa procedura descrivono come configurare un certificato da un'autorità di certificazione radice aziendale (CA) interna distribuita dall'organizzazione e con l'elaborazione delle richieste offline. Per informazioni dettagliate su come ottenere certificati da una CA esterna, contattare il team di supporto.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>Per configurare i certificati per il pool di Director o Director

1.  Nella distribuzione guidata di Lync Server, accanto al **passaggio 3: Richiedi, installa o assegna certificati**, fai clic su **Esegui**.

2.  Nella pagina **creazione guidata certificato** fare clic su **Richiedi**.

3.  Nella pagina **richiesta certificato** fare clic su **Avanti**.

4.  Nella pagina **richieste immediate o posticipate** accettare il **messaggio di richiesta predefinito invia immediatamente l'opzione a un'autorità di certificazione online** e quindi fare clic su **Avanti**.

5.  Nella pagina **Scegli autorità di certificazione (CA)** fare clic sull'autorità di certificazione Windows interna che si vuole usare e quindi fare clic su **Avanti**.

6.  Nella pagina dell' **account dell'autorità di certificazione** specificare le credenziali alternative da usare se l'account con cui si è connessi non dispone dell'autorità sufficiente per richiedere il certificato e quindi fare clic su **Avanti**.

7.  Nella pagina **Specifica modello di certificato alternativo** fare clic su **Avanti**.

8.  Nella pagina **Impostazioni nome e sicurezza** è possibile specificare un **nome descrittivo**, accettare la lunghezza della chiave di 2048 bit e quindi fare clic su **Avanti**.

9.  Nella pagina **informazioni organizzazione** , facoltativamente, specificare le informazioni sull'organizzazione e quindi fare clic su **Avanti**.

10. Nella pagina **informazioni geografiche** specificare facoltativamente informazioni geografiche e quindi fare clic su **Avanti**.

11. Nella pagina **nome oggetto/nomi alternativi oggetto** fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > L'elenco nome alternativo oggetto deve contenere il nome del computer in cui si sta installando il Director (se un singolo amministratore) o il nome del pool di Director e i nomi di URL semplici configurati per l'organizzazione.

    
    </div>

12. Nell' **impostazione del dominio SIP nella pagina nome alternativo soggetto (sans)** selezionare i **domini SIP configurati** per tutti i domini che si desidera vengano gestiti dal Director e quindi fare clic su **Avanti**.

13. Nella pagina **Configura altri nomi alternativi** per l'oggetto aggiungere eventuali nomi alternativi di altri soggetti obbligatori e quindi fare clic su **Avanti**.

14. Nella pagina **Riepilogo richiesta di certificato** fare clic su **Avanti**.

15. Nella pagina **esecuzione dei comandi** fare clic su **Avanti** dopo che i comandi hanno terminato l'esecuzione.

16. Nella pagina **stato richiesta di certificato online** fare clic su **fine**.

17. Nella pagina **assegnazione certificato** fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Se si vuole visualizzare il certificato, fare doppio clic sul certificato nell'elenco.

    
    </div>

18. Nella pagina **Riepilogo assegnazione certificati** fare clic su **Avanti**.

19. Nella pagina **esecuzione dei comandi** fare clic su **fine** dopo che i comandi hanno terminato l'esecuzione.

20. Nella pagina **creazione guidata certificato** fare clic su **Chiudi**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

