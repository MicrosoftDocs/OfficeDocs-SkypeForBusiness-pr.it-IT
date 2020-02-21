---
title: Distribuzione di una porta non standard e di un alias di SQL Server in Lync Server 2013
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
ms.openlocfilehash: 51d102c6a810730d6c748dafc6a4fcdc3dd6821e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a>Distribuzione di una porta non standard e di un alias di SQL Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-09-16_

Microsoft Lync Server 2013 supporta l'utilizzo di una porta non standard e di un alias in SQL Server. L'utilizzo di una porta non standard di SQL Server e di un alias aumenta la sicurezza e crea un ambiente più flessibile per la distribuzione di Lync. Questi passaggi sono solo un singolo passaggio per garantire il corretto funzionamento dell'ambiente Lync Server 2013. È necessario eseguire ulteriori operazioni per ridurre la superficie di attacco di un'implementazione di Lync Server 2013.

Nell'articolo seguente vengono descritti i passaggi necessari per configurare una porta non standard e un alias di SQL Server in Lync Server 2013.

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a>Distribuzione di una porta non standard e di un alias di SQL Server in Lync Server 2013

Il generatore di topologie di Lync Server 2013 supporta l'utilizzo di un alias di SQL Server come nome di dominio completo (FQDN) anziché come FQDN effettivo di SQL Server durante la configurazione di Lync Server 2013. In questo modo il nome FQDN effettivo di SQL Server deve essere nascosto da qualsiasi utente malintenzionato. Inoltre, l'utilizzo di una porta non standard nasconde la porta effettiva da qualsiasi utente malintenzionato che tenta di attaccare il database sulla porta standard 1433, come illustrato nella figura seguente.

![Un hacker non conosce il numero di porta da attaccare.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "Un hacker non conosce il numero di porta da attaccare.")

Per avere esito positivo nel determinare la porta che Lync Server 2013 utilizza per comunicare con SQL Server, l'utente malintenzionato dovrà analizzare tutte le porte per ottenere le informazioni sulla porta. L'analisi di una porta eseguita da un utente malintenzionato aumenta le possibilità che la sicurezza possa rilevare e arrestare l'istruzione. Oltre ad aggiungere maggiore sicurezza con una porta non standard, è anche possibile utilizzare un alias di SQL Server per fornire flessibilità per la distribuzione. Ciò è utile per ridurre le modifiche apportate alla configurazione in situazioni in cui è necessaria una modifica del nome di SQL Server.

<div>


> [!NOTE]  
> In SQL Server sono disponibili due metodi di tolleranza di errore (clustering di failover e mirroring). Entrambi i metodi di tolleranza di errore di SQL Server sono supportati utilizzando una porta non standard e un alias di SQL Server con Lync Server 2013. Se il backend di SQL Server utilizzato dal pool è in una configurazione con mirroring, è necessario che il servizio SQL browser sui server back-end di SQL Server sia in esecuzione affinché i server front endpoint si connettano al database con mirroring quando i database non vengono riavviati nell'SQL con mirroring. Server.



</div>

Quando si configura la connettività dei database di SQL Server dall'interno di generatore di topologie o quando si utilizza il cmdlet Install-CsDatabase, non è possibile definire in modo esplicito un numero di porta non standard di SQL Server e associarlo a un'istanza di SQL. Per impostare una porta non standard, è necessario utilizzare le utilità SQL Server e Windows Server.

Per impostare una porta non standard e un alias di SQL Server per l'utilizzo con Lync Server 2013, sarà necessario completare tre passaggi principali. I passaggi sono i seguenti:

  - Verificare che in Lync Server 2013 siano stati applicati gli aggiornamenti più recenti.

  - Configurare la porta non standard e l'alias di SQL Server.

  - Configurare Lync Server 2013 con l'alias di SQL Server tramite Generatore di topologie.

  - Pubblicare la topologia e verificare il database.

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a>Verificare che in Lync Server 2013 siano stati applicati gli aggiornamenti più recenti

È importante mantenere Lync Server 2013 aggiornato. Per verificare la disponibilità degli aggiornamenti e delle informazioni più recenti su come applicarli, vedere [Updates for Lync Server 2013](https://support.microsoft.com/kb/2809243).

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a>Configurare la porta e l'alias di SQL Server non standard

La porta non standard e l'alias di SQL Server devono essere configurati nell'istanza del database prima di poter fare riferimento a un generatore di topologie di Lync Server 2013. Per impostare una porta non standard e un alias di SQL Server, sarà necessario completare tre passaggi principali. Questi passaggi sono i seguenti:

  - Modificare i valori predefiniti del protocollo TCP/IP.

  - Creare e configurare un alias di SQL Server.

  - Creare un record di risorse DNS (Domain Name System) (CNAME).

**Modificare i valori predefiniti del protocollo TCP/IP**

1.  Fare clic su **Start**e scegliere **Gestione configurazione SQL Server**, come illustrato nella figura seguente.
    
    ![Icona di SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icona di SQL Server Management Studio")

2.  Nel riquadro di spostamento scegliere di espandere l' **istanza di SQL Server**, scegliere di espandere **configurazione di rete di SQL Server**e scegliere **protocolli \<come nome\>di istanza**, come illustrato nella figura seguente.
    
    ![Passare a proprietà TCP/IP](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Passare a proprietà TCP/IP")

3.  Nel riquadro destro fare clic con il pulsante destro del mouse su **TCP/IP**e scegliere **Proprietà**. Verrà visualizzata la finestra di dialogo Proprietà TCP/IP.

4.  Selezionare la scheda **indirizzi IP** . La scheda indirizzi IP Visualizza tutti gli indirizzi IP attivi sul server. Si tratta del formato IP1, IP2, fino a IPAll, come illustrato nella figura seguente.
    
    ![Aprire le proprietà TCP/IP.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Aprire le proprietà TCP/IP.")

5.  Cancellare il campo **porte dinamiche TCP** per tutti gli indirizzi IP. Se il campo contiene un carattere zero, significa che SQL Server è in attesa su porte dinamiche. Verificare che questi campi siano deselezionati e che non contengano uno zero.

6.  Per l'indirizzo IP che verrà utilizzato da Lync Server per la connessione al database, verificare che **Enabled** sia impostato su **Sì**, come illustrato nella figura seguente.
    
    ![Impostare attivato come Sì per l'indirizzo IP corretto.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Impostare attivato come Sì per l'indirizzo IP corretto.")

7.  Nella sezione **IPAll** nella parte inferiore della finestra di dialogo, immettere la porta desiderata nel campo **porta TCP** , come illustrato nella figura seguente. In questo esempio viene utilizzata la porta 50062, ma è possibile utilizzare qualsiasi porta tra 49152 e 65535. Si tratta delle porte assegnate a un utilizzo dinamico e privato e questo garantisce che non vi siano conflitti con le altre porte utilizzate nella distribuzione di Lync Server 2013.
    
    ![Impostare la porta nella sezione IPAll.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Impostare la porta nella sezione IPAll.")

8.  Fare clic su **OK** per uscire dalla finestra di dialogo delle proprietà TCP/IP.

9.  Riavviare l'istanza di SQL Server selezionando **servizi SQL Server** nel riquadro sinistro di gestione configurazione SQL Server. Fare quindi clic con il pulsante destro del mouse su **nome \<\> dell'istanza di SQL Server** nel riquadro destro e scegliere **Riavvia**, come illustrato nella figura seguente.
    
    ![Reimpostare il servizio SQL Server per l'istanza.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reimpostare il servizio SQL Server per l'istanza.")

<div>


> [!IMPORTANT]  
> Assicurarsi di aggiornare le impostazioni del firewall per ospitare la nuova porta di SQL Server.



</div>

**Creare e configurare un alias di SQL Server**

1.  Fare clic su **Start**e scegliere **Gestione configurazione SQL Server**, come illustrato nella figura seguente.
    
    ![Icona di SQL Server Management Studio](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "Icona di SQL Server Management Studio")

2.  Nel riquadro sinistro scegliere Espandi **istanza di SQL Server**, fare clic su Espandi **Configurazione versione \<\> SQL Native Client**e quindi scegliere **alias**, come illustrato nella figura seguente.
    
    ![Alias in Gestione configurazione SQL Server.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Alias in Gestione configurazione SQL Server.")

3.  Fare clic con il pulsante destro del mouse su **alias**e scegliere **nuovo alias...**.

4.  Immettere il **nome dell'alias**, il **numero di porta**, il **protocollo**e il **Server**, come illustrato nella figura seguente.
    
    ![Creazione di un nuovo alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creazione di un nuovo alias")
    
    <div>
    

    > [!CAUTION]  
    > Assicurarsi di immettere la stessa porta non standard utilizzata nel passaggio precedente, poiché quella è la porta che verrà ascoltata da SQL Server. Se un alias configurato è connesso all'istanza o all'FQDN di SQL Server errato, disabilitare e quindi riattivare il protocollo di rete associato. In questo modo vengono eliminate tutte le informazioni sulla connessione memorizzate nella cache e il client si connette correttamente.

    
    </div>

**Creare un record di risorse DNS CNAME**

1.  Accedere al computer che gestisce DNS.

2.  Fare clic su **Start**e scegliere **Server Manager**, come illustrato nella figura seguente.
    
    ![Apertura di Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Apertura di Server Manager")

3.  Scegliere il menu a discesa **strumenti** e selezionare **DNS**, come illustrato nella figura seguente.
    
    ![Apertura di DNS da Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Apertura di DNS da Server Manager.")

4.  Nel riquadro sinistro espandere il nodo nome server, espandere il nodo zone di ricerca diretta e scegliere il dominio pertinente.

5.  Fare clic con il pulsante destro del mouse sul dominio e scegliere **nuovo alias (CNAME)...**, come illustrato nella figura seguente.
    
    ![Selezionare l'opzione per creare un nuovo alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selezionare l'opzione per creare un nuovo alias CNAME")

6.  Immettere il **nome dell'alias** e l' **FQDN per SQL Server**, come illustrato nella figura seguente.
    
    ![Compilazione della nuova finestra di dialogo CNAME alias.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Compilazione della nuova finestra di dialogo CNAME alias.")

7.  Scegliere **OK** per salvare CNAME e visualizzarlo in gestione DNS.

</div>

<div>

## <a name="validate-database-connectivity"></a>Convalidare la connettività dei database

Esistono diversi modi per assicurarsi che funzioni. Si desidera verificare che il database di SQL Server sia in attesa sulla porta specificata utilizzando l'alias. Un controllo rapido può essere completato utilizzando i comandi **netstat** e **Telnet** .

<div>


> [!NOTE]  
> Il client Telnet è una funzionalità che viene fornita con Windows Server, ma che deve essere installata. È possibile installare una funzionalità di Windows Server aprendo Server Manager e selezionando Aggiungi ruoli e funzionalità dal menu Gestisci.



</div>

**Utilizzo di netstat e Telnet per verificare la connettività dei database**

1.  Fare clic su **Start**e digitare **cmd** per aprire un prompt di comandi.

2.  Digitare **netstat-a-f**e verificare che SQL Server sia in esecuzione con la porta corretta, come illustrato nella figura seguente.
    
    ![Utilizzo di netstat per verificare la porta.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Utilizzo di netstat per verificare la porta.")

3.  Digitare **la \<\> \<porta \# nome Telnet alias** per confermare la connessione all'istanza di SQL Server. Se la connessione ha esito positivo, Telnet si collegherà e non dovrebbe essere visualizzato un errore. Questo dimostra che l'istanza di SQL Server è in ascolto sulla porta corretta con l'alias corretto. Se si verifica un problema di connessione al database di SQL Server, viene visualizzato un errore che indica che non è possibile effettuare la connessione. Dopo aver verificato la connettività dei database nel server di database, è possibile eseguire la stessa operazione da Lync Server (sulla rete) e assicurarsi che non vi siano firewall che impediscono l'accesso lungo la strada.

</div>

<div>

## <a name="conclusion"></a>Conclusione

Dopo aver configurato l'alias di SQL Server, è possibile utilizzarlo per creare una topologia di Lync Server 2013 nello strumento generatore di topologie. Per ulteriori informazioni sulle topologie, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

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

