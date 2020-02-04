---
title: Distribuzione di una porta e di un alias non standard di SQL Server in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fffa3502b04a9d05387cd94e157ed183e1fe32ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Distribuzione di una porta e di un alias non standard di SQL Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-09-16_

Microsoft Lync Server 2013 supporta l'uso di una porta e un alias non standard in SQL Server. L'uso di una porta non standard di SQL Server e di un alias aumenta la sicurezza e crea un ambiente più flessibile per la distribuzione di Lync. Questi passaggi sono solo un singolo passaggio per proteggere correttamente l'ambiente Lync Server 2013. È necessario eseguire ulteriori operazioni per ridurre la superficie di attacco di un'implementazione di Lync Server 2013.

L'articolo seguente descrive i passaggi necessari per configurare una porta non standard e un alias di SQL Server in Lync Server 2013.

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Distribuzione di una porta e un alias non standard di SQL Server in Lync Server 2013

Il generatore di topologia di Lync Server 2013 supporta l'uso di un alias di SQL Server come nome di dominio completo (FQDN) anziché l'FQDN effettivo di SQL Server durante la configurazione di Lync Server 2013. In questo modo l'FQDN effettivo di SQL Server deve essere nascosto da qualsiasi utente malintenzionato. Inoltre, l'uso di una porta non standard oscura la porta effettiva da qualsiasi utente malintenzionato tenti di attaccare il database nella porta standard 1433, come illustrato nella figura seguente.

![Un pirata informatico non conosce il numero di porta da attaccare.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un pirata informatico non conosce il numero di porta da attaccare.")

Per avere successo nel determinare la porta che Lync Server 2013 USA per comunicare con SQL Server, l'aggressore dovrà analizzare tutte le porte per ottenere le informazioni sulla porta. Un'analisi della porta da parte di un utente malintenzionato aumenta le probabilità che la sicurezza possa rilevare e interrompere l'istruzione. Oltre ad aggiungere maggiore sicurezza con una porta non standard, puoi anche usare un alias di SQL Server per garantirti la flessibilità per la distribuzione. Questa operazione è utile per ridurre le modifiche alla configurazione nelle situazioni in cui è necessaria una modifica del nome di SQL Server.

<div>


> [!NOTE]  
> SQL Server offre due metodi di tolleranza dell'errore (clustering di failover e mirroring). Entrambi i metodi di tolleranza di errore di SQL Server sono supportati usando una porta non standard di SQL Server e un alias con Lync Server 2013. Se il backend di SQL Server usato dal pool si trova in una configurazione con mirroring, il servizio SQL browser nei server di backend di SQL Server dovrebbe essere in funzione per i server front-end per connettersi al database con mirroring quando i database non vengono superati nell'SQL con mirroring Server.



</div>

Quando si configura la connettività di database di SQL Server dall'interno del generatore di topologia o quando si usa il cmdlet Install-CsDatabase, non è possibile definire in modo esplicito un numero di porta non standard di SQL Server e associarlo a un'istanza SQL. Per impostare una porta non standard, è necessario usare le utilità SQL Server e Windows Server.

Per configurare una porta e un alias di SQL Server non standard da usare con Lync Server 2013, sarà necessario completare tre passaggi principali. Questi passaggi sono i seguenti:

  - Verificare che in Lync Server 2013 siano applicati gli aggiornamenti più recenti.

  - Configurare la porta e l'alias non standard di SQL Server.

  - Configurare Lync Server 2013 con l'alias di SQL Server tramite Generatore di topologie.

  - Pubblicare la topologia e verificare il database.

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Verificare che in Lync Server 2013 siano applicati gli aggiornamenti più recenti

È importante impedire che Lync Server 2013 sia aggiornato. Per verificare la disponibilità degli aggiornamenti più recenti e delle informazioni su come applicarli, vedere [aggiornamenti per Lync Server 2013](http://support.microsoft.com/kb/2809243).

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>Configurare la porta non standard e l'alias di SQL Server

La porta e l'alias di SQL Server non standard devono essere configurati nell'istanza del database prima di poter fare riferimento a un generatore di topologia di Lync Server 2013. Per configurare una porta e un alias di SQL Server non standard, sarà necessario completare tre passaggi principali. Questi passaggi sono i seguenti:

  - Modificare i valori di protocollo TCP/IP predefiniti.

  - Creare e configurare un alias di SQL Server.

  - Creare un record di risorse DNS (Domain Name System) (CNAME) nome canonico.

**Modificare i valori di protocollo TCP/IP predefiniti**

1.  Selezionare **Start**e scegliere **Gestione configurazione SQL Server**, come illustrato nella figura seguente.
    
    ![Icona di SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icona di SQL Server Management Studio")

2.  Nel riquadro di spostamento scegliere per espandere l' **istanza di SQL Server**, scegliere Espandi **configurazione di rete SQL Server**e scegliere **protocolli per \<il nome\>dell'istanza**, come illustrato nella figura seguente.
    
    ![Passare alle proprietà TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Passare alle proprietà TCP/IP")

3.  Nel riquadro destro fare clic con il pulsante destro del mouse su **TCP/IP**e scegliere **Proprietà**. Viene visualizzata la finestra di dialogo Proprietà TCP/IP.

4.  Selezionare la scheda **indirizzi IP** . La scheda indirizzi IP Mostra tutti gli indirizzi IP attivi nel server. Questi sono nel formato IP1, IP2, fino a IPAll, come illustrato nella figura seguente.
    
    ![Aprire le proprietà TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Aprire le proprietà TCP/IP.")

5.  Deselezionare il campo **porte dinamiche TCP** per tutti gli indirizzi IP. Se il campo contiene un carattere zero, significa che SQL Server è in ascolto sulle porte dinamiche. Verificare che questi campi siano deselezionati e che non contengano uno zero.

6.  Per l'indirizzo IP che verrà usato da Lync Server per la connessione al database, verificare che **Enabled** sia impostato su **Sì**, come illustrato nella figura seguente.
    
    ![Impostare Abilitato su Sì per l'indirizzo IP corretto.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Impostare Abilitato su Sì per l'indirizzo IP corretto.")

7.  Nella sezione **IPAll** nella parte inferiore della finestra di dialogo immettere la porta desiderata nel campo della **porta TCP** , come illustrato nella figura seguente. In questo esempio usiamo la porta 50062, ma è possibile usare qualsiasi porta tra 49152 e 65535. Queste sono le porte assegnate a un uso dinamico e privato e questo garantisce che non ci siano conflitti con altre porte usate nella distribuzione di Lync Server 2013.
    
    ![Impostare la porta nella sezione IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Impostare la porta nella sezione IPAll.")

8.  Scegliere **OK** per uscire dalla finestra di dialogo Proprietà TCP/IP.

9.  Riavviare l'istanza di SQL Server selezionando **servizi SQL Server** nel riquadro sinistro di gestione configurazione SQL Server. Fare quindi clic con il pulsante destro del mouse su **nome \<\> istanza di SQL Server** nel riquadro destro e scegliere **Riavvia**, come illustrato nella figura seguente.
    
    ![Reimpostare il servizio SQL Server per l'istanza.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reimpostare il servizio SQL Server per l'istanza.")

<div>


> [!IMPORTANT]  
> Assicurarsi di aggiornare le impostazioni del firewall in modo che siano adatte alla nuova porta di SQL Server.



</div>

**Creare e configurare un alias di SQL Server**

1.  Selezionare **Start**e scegliere **Gestione configurazione SQL Server**, come illustrato nella figura seguente.
    
    ![Icona di SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icona di SQL Server Management Studio")

2.  Nel riquadro sinistro scegliere Espandi **istanza di SQL Server**, scegliere di espandere la **configurazione della versione\> di \<SQL Native Client**e quindi scegliere **alias**, come illustrato nella figura seguente.
    
    ![Alias in Gestione configurazione SQL Server.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias in Gestione configurazione SQL Server.")

3.  Fare clic con il pulsante destro del mouse su **alias**e scegliere **nuovo alias.**

4.  Immettere il **nome dell'alias**, il **numero di porta**, il **protocollo**e il **Server**, come illustrato nella figura seguente.
    
    ![Creazione di un nuovo alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creazione di un nuovo alias")
    
    <div>
    

    > [!CAUTION]  
    > Assicurarsi di immettere la stessa porta non standard usata nel passaggio precedente, perché la porta verrà ascoltata da SQL Server. Se un alias configurato si connette all'istanza o al nome FQDN di SQL Server errato, disabilitare e quindi riattivare il protocollo di rete associato. Questa operazione cancella le informazioni sulla connessione memorizzate nella cache e consente al client di connettersi correttamente.

    
    </div>

**Creare un record di risorse DNS CNAME**

1.  Accedere al computer per la gestione del DNS.

2.  Selezionare **Start**e scegliere **Server Manager**, come illustrato nella figura seguente.
    
    ![Apertura di Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Apertura di Server Manager")

3.  Scegliere l'elenco a discesa **strumenti** e selezionare **DNS**, come illustrato nella figura seguente.
    
    ![Apertura di DNS da Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Apertura di DNS da Server Manager.")

4.  Nel riquadro sinistro espandere il nodo nome server, espandere il nodo zone di ricerca in avanti e scegliere il dominio pertinente.

5.  Fare clic con il pulsante destro del mouse sul dominio e scegliere **nuovo alias (CNAME)...**, come illustrato nella figura seguente.
    
    ![Selezione dell'opzione per creare un nuovo alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selezione dell'opzione per creare un nuovo alias CNAME")

6.  Immettere il **nome dell'alias** e l' **FQDN per SQL Server**, come illustrato nella figura seguente.
    
    ![Compilazione della finestra di dialogo del nuovo alias CNAME.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Compilazione della finestra di dialogo del nuovo alias CNAME.")

7.  Scegliere **OK** per salvare il CNAME e visualizzarlo in DNS Manager.

</div>

<div>

## <a name="validate-database-connectivity"></a>Convalidare la connettività del database

Esistono molti modi diversi per verificare che funzioni. Si vuole verificare che il database di SQL Server sia in ascolto sulla porta specificata usando l'alias. Un controllo rapido può essere completato usando i comandi **netstat** e **Telnet** .

<div>


> [!NOTE]  
> Client Telnet è una funzionalità fornita con Windows Server, ma che deve essere installata. Una caratteristica di Windows Server può essere installata aprendo Server Manager e selezionando Aggiungi ruoli e funzionalità dal menu Gestisci.



</div>

**Usare netstat e Telnet per verificare la connettività del database**

1.  Selezionare **Start**e digitare **cmd** per aprire un prompt dei comandi.

2.  Digitare **netstat-a-f**e verificare che SQL Server sia in uso con la porta corretta, come illustrato nella figura seguente.
    
    ![Utilizzo di netstat per il controllo della porta.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Utilizzo di netstat per il controllo della porta.")

3.  Digitare **Telnet \<alias\> \<Port \# ** per confermare la connessione all'istanza di SQL Server. Se la connessione ha esito positivo, Telnet si connette e non dovrebbe essere visualizzato un messaggio di errore. Questo dimostra che l'istanza di SQL Server sta ascoltando la porta corretta con l'alias corretto. In caso di problemi di connessione al database di SQL Server, Telnet Mostra un errore che la connessione non può essere eseguita. Ora che è stata selezionata la connettività del database nel server di database, è possibile eseguire la stessa operazione da Lync Server (tramite la rete) e verificare che non ci siano firewall che bloccano l'accesso lungo il percorso.

</div>

<div>

## <a name="conclusion"></a>Conclusione

Dopo aver configurato l'alias di SQL Server, è possibile usarlo per creare una topologia di Lync Server 2013 nello strumento generatore di topologia. Per altre informazioni sulle topologie, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[pianificazione della sicurezza in Lync Server 2013](lync-server-2013-planning-for-security.md)  
[Definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md)  
[Distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

