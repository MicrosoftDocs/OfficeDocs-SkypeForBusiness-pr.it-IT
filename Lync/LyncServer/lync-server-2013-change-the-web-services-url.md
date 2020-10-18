---
title: "Lync Server 2013: modificare l'URL dei servizi Web"
description: "Lync Server 2013: modificare l'URL dei servizi Web."
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
ms.openlocfilehash: 78a7a9b70d475aa952a43d215a8e5cd2068911e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576352"
---
# <a name="change-the-web-services-url-in-lync-server-2013"></a>Modificare l'URL dei servizi Web in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-11-16_

Quando si impostano i pool Front End e i Server Standard, si ha la possibilità di configurare il nome di dominio completo (FQDN) di una Web farm esterna e le porte associate. Se non è stato configurato questo URL quando è stata eseguita la distribuzione guidata di Lync Server, è necessario configurare manualmente tali impostazioni. Un amministratore in genere non ha necessità di modificare tali impostazioni, dal momento che si tratta delle porte consigliate e predefinite.

<div>


> [!NOTE]  
> La schermata seguente è stata scattata durante la configurazione di un server Standard Edition, quindi l'opzione Sostituisci FQDN è disattivata. Questa opzione è abilitata durante la configurazione di un server Enterprise Edition in un pool Front end.



</div>

![Modificare le impostazioni del pool di servizi Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Modificare le impostazioni del pool di servizi Web")

<div>

## <a name="to-configure-web-services"></a>Per configurare i servizi Web

1.  Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

3.  In Generatore di topologie, nell'albero della console in **Standard Edition Front End Server**, **pool Enterprise Edition front end**e **pool di directory**selezionare il nome del pool. Fare clic con il pulsante destro del mouse sul nome, scegliere **Modifica proprietà** e quindi fare clic su **Servizi Web**.

4.  Aggiungere o modificare l'FQDN di **Servizi Web esterni** e quindi fare clic su **OK**.
    
    <div>
    

    > [!WARNING]  
    > Se si dispone di più di un pool Front end o front end server, l'FQDN dei servizi Web esterni deve essere univoco. Ad esempio, se si definisce l'FQDN dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile utilizzare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front end o front end server. Se si sta distribuendo anche Director, l'FQDN dei servizi Web esterni definiti per qualsiasi server Director o di server Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front end o front-end.

    
    </div>

5.  Verificare che le porte di attesa e pubblicate siano configurate correttamente per l'ambiente.

6.  Ripetere questi passaggi per tutti i server Standard Edition, i pool Front End e i pool di server Director nell'ambiente.

7.  Nell'albero della console fare clic su **Lync Server 2013** e quindi fare clic su **Pubblica topologia** nel riquadro **Azioni**.

Per la configurazione delle porte di attesa e pubblicate è necessario tenere conto di alcuni requisiti:

  - Le porte di attesa visualizzate sono quelle configurate per Internet Information Server (IIS) in ogni Front End Server.

  - Le porte di attesa interne ed esterne devono essere diverse per IIS. Per le porte di attesa esterne, queste sono in genere le stesse perché una rappresenta il dispositivo di bilanciamento del carico hardware per il traffico Web interno e una rappresenta il server proxy inverso per il traffico Web esterno.

  - È possibile sostituire i servizi Web interni in un pool Front End, in un server Director o in un pool di Director e definire il nome di dominio completo.
    
    <div>
    

    > [!WARNING]  
    > Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.

    
    </div>

  - Le porte pubblicate devono essere configurate nel proxy inverso o nel dispositivo di bilanciamento del carico hardware come porte di attesa.

  - Per un pool Front End (non mostrato nell'esempio, l'FQDN del pool SIP interno deve essere diverso dall'FQDN dei Servizi Web interni, perché il traffico Web arriva attraverso il dispositivo di bilanciamento del carico hardware e il traffico del pool SIP interno passa attraverso il servizio di bilanciamento del carico DNS. Questo requisito deve essere soddisfatto.

  - Una distribuzione di Lync Server Standard Edition non richiede o consente l'override di un FQDN dei servizi Web interni perché questo server non è in grado di bilanciare il carico.

  - Se nel proprio ambiente si dispone di un dispositivo di bilanciamento del carico hardware utilizzato sia per il traffico SIP interno che per quello Web, il generatore di topologie non è in grado di effettuare la distinzione.
    
    Gli FQDN dei servizi Web devono essere facilmente differenziati l'uno dall'altro; Questo aiuta a garantire che i client punti di reindirizzamento URL verso il server appropriato. Ad esempio, se si dispone di due FQDN, è possibile prendere in considerazione la denominazione di un meeting.contoso.com e l'altro conferencing.contoso.com. È possibile che si verifichino problemi di reindirizzamento se sono presenti FQDN con nomi simili, ad esempio meet1.contoso.com e meet2.contoso.com.

I servizi Web esterni operano in combinazione con un proxy inverso nella rete perimetrale. Consente ai client di accedere all'esterno utilizzando questi servizi Web. Gli FQDN configurati in questo articolo vengono inviati ai client quando eseguono l'accesso e vengono utilizzati per riportare una connessione HTTPS al proxy inverso quando si effettua la connessione in remoto. Il server proxy inverso inoltra il nome di dominio completo del servizio Web esterno a un dispositivo di bilanciamento del carico hardware interno o direttamente al pool. Il proxy inverso deve essere in grado di risolvere il nome di dominio completo dei servizi Web esterni nell'indirizzo IP del server Web interno. L'nome dei servizi Web esterni deve essere risolvibile nella rete Internet pubblica.

Se il server interno è un server Standard Edition, il nome di dominio completo interno è il nome di dominio completo del server Standard Edition. Se il server interno è un pool Front End, l'FQDN è un IP virtuale (VIP) dello strumento di bilanciamento del carico hardware che gestisce il bilanciamento del carico dei server della Web farm interna. È necessario un dispositivo di bilanciamento del carico hardware in un pool Front End con più di un server Enterprise Edition. Non è invece necessario per un server Standard Edition o un singolo Enterprise Edition Front End Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

