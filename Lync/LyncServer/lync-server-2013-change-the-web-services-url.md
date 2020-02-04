---
title: "Lync Server 2013: modificare l'URL dei servizi Web"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934e448f48413df2938deab8a0d08389cfad37bd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>Modificare l'URL dei servizi Web in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-11-16_

Quando si configurano i pool Front-end e i server Standard Edition, è possibile configurare un nome di dominio completo (FQDN) di una Web farm esterna e le porte associate. Se non è stato configurato questo URL quando è stata eseguita la distribuzione guidata di Lync Server, è necessario configurare manualmente queste impostazioni. In genere, un amministratore non deve modificare queste impostazioni, perché queste sono le porte consigliate e predefinite.

<div>


> [!NOTE]  
> La schermata seguente è stata scattata durante la configurazione di un server Standard Edition, quindi l'opzione Sostituisci FQDN è disabilitata. Questa opzione è abilitata quando si configura un server Enterprise Edition in un pool Front-end.



</div>

![Modificare le impostazioni dei pool per i servizi Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Modificare le impostazioni dei pool per i servizi Web")

<div>

## <a name="to-configure-web-services"></a>Per configurare i servizi Web

1.  Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

3.  In Generatore di topologia, nell'albero della console, in **server front-end Standard Edition**, **pool di front end Enterprise Edition**e **pool di directory**, selezionare il nome del pool. Fare clic con il pulsante destro del mouse sul nome, scegliere **modifica proprietà**e quindi fare clic su **servizi Web**.

4.  Aggiungere o modificare il **nome di dominio completo dei servizi Web esterni**e quindi fare clic su **OK**.
    
    <div>
    

    > [!WARNING]  
    > Se si hanno più di un pool Front end o un server front-end, l'FQDN dei servizi Web esterni deve essere univoco. Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile usare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front-end o front end server. Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server.

    
    </div>

5.  Verificare che le porte in attesa e pubblicate siano configurate correttamente per l'ambiente.

6.  Ripetere questi passaggi per tutti i server Standard Edition, i pool Front-end e i pool di Director nell'ambiente.

7.  Nell'albero della console fare clic su **Lync Server 2013**e quindi, nel riquadro **azioni** , fare clic su **Pubblica topologia**.

Quando si configurano le porte di ascolto e di pubblicazione, è necessario tenere presenti alcuni requisiti:

  - Le porte in attesa visualizzate sono le porte configurate per Internet Information Server (IIS) in ogni server front-end.

  - Le porte di ascolto interne ed esterne devono essere diverse per IIS. Per le porte di ascolto esterne, si tratta in genere dello stesso perché uno rappresenta il bilanciamento del carico hardware per il traffico Web interno e uno rappresenta il server proxy inverso per il traffico Web esterno.

  - È possibile ignorare i servizi Web interni in un pool di front-end, un Director o un pool di Director e definire il proprio nome di dominio completo.
    
    <div>
    

    > [!WARNING]  
    > Se si decide di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, direttore o pool di Director.

    
    </div>

  - Le porte pubblicate devono essere configurate nel proxy inverso o nel bilanciamento del carico hardware come porte di ascolto.

  - Per un pool Front-End (non illustrato nell'esempio), il nome di dominio completo del pool SIP interno deve essere diverso dall'FQDN dei servizi Web interni, perché il traffico Web passa attraverso il servizio di bilanciamento del carico hardware e il traffico del pool SIP interno passa attraverso il servizio di bilanciamento del carico DNS . Questo requisito deve essere soddisfatto.

  - Una distribuzione di Lync Server Standard Edition non richiede o consente l'override di un FQDN dei servizi Web interni perché questo server non può essere caricato in modo equilibrato.

  - Se si dispone di un dispositivo di bilanciamento del carico hardware nell'ambiente usato sia per il traffico SIP interno che per quello Web, il generatore di topologie non può distinguere.
    
    Gli FQDN dei servizi Web devono essere facilmente differenziati l'uno dall'altro; Questo consente di garantire che i client punti di reindirizzamento degli URL verso il server appropriato. Se ad esempio sono presenti due nomi di dominio completi, è possibile considerare la denominazione di un meeting.contoso.com e l'altro conferencing.contoso.com. Se si hanno nomi di dominio completi, ad esempio meet1.contoso.com e meet2.contoso.com, è possibile che si possano eseguire potenziali problemi di reindirizzamento.

I servizi Web esterni funzionano in combinazione con un proxy inverso nella rete perimetrale. Offre ai client l'accesso esterno tramite questi servizi Web. I nomi di dominio completi configurati in questo articolo vengono inviati ai client durante l'accesso e vengono usati per ripristinare una connessione HTTPS al proxy inverso quando si connette in remoto. Il server proxy inverso inoltra il nome di dominio completo del servizio Web esterno a un bilanciamento del carico hardware interno o direttamente al pool. Il proxy inverso deve essere in grado di risolvere il nome di dominio completo dei servizi Web esterni con l'indirizzo IP del server Web interno. I servizi Web esterni FDQN devono essere risolvibili in Internet pubblico.

Se il server interno è un server Standard Edition, il nome di dominio completo interno è il nome di dominio completo del server Standard Edition. Se il server interno è un pool Front-End, il nome completo è un IP virtuale (VIP) di bilanciamento del carico hardware che bilancia il carico dei server della Web farm interna. Un bilanciamento del carico hardware è obbligatorio in un pool Front-end con più server Enterprise Edition. Un tipo di bilanciamento del carico non è necessario per un server Standard Edition o un server front-end singolo Enterprise Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

