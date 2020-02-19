---
title: "Lync Server 2013: registrazione degli utenti per l'autenticazione con smart card"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 635565936712fe542c807ea4d4c65f584e836bdc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Registrazione degli utenti per l'autenticazione con smart card in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-03_

Sono in genere disponibili due metodi per la registrazione di utenti per l'autenticazione con smart card. Il metodo più semplice consiste nel fatto che gli utenti si iscrivono direttamente per l'autenticazione con smart card tramite la registrazione Web, mentre il metodo più complesso implica l'utilizzo di un agente di registrazione. Questo argomento è dedicato alla registrazione automatica dei certificati smartcard.

Per ulteriori informazioni sull'iscrizione a nome degli utenti come agente di registrazione, vedere registrazione dei certificati per conto di altri utenti all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>Per registrare gli utenti per l'autenticazione con smart card

1.  Accedere alla workstation Windows 8 utilizzando le credenziali di un utente abilitato per Lync.

2.  Avviare Internet Explorer.

3.  Passare alla pagina **registrazione Web Authority Certificate** (ad esempio https://MyCA.contoso.com/certsrv),.
    
    <div>
    

    > [!NOTE]  
    > Se si utilizza Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità.

    
    </div>

4.  Nella pagina **iniziale** , selezionare **Richiedi un certificato**.

5.  Successivamente, selezionare **richiesta avanzata**.

6.  Selezionare **Crea e invia una richiesta a questa CA**.

7.  Selezionare **utente smartcard** nella sezione **modello di certificato** e completare la richiesta di certificato avanzato con i valori seguenti:
    
      - Le **Opzioni principali** confermano le impostazioni seguenti:
        
          - Selezionare il pulsante di opzione **Crea nuovo set di tasti**
        
          - Per **CSP**, selezionare **Microsoft Base Smart Card Crypto Provider**
        
          - Per l' **utilizzo della chiave**, selezionare **Exchange** (è l'unica opzione disponibile).
        
          - Per le **dimensioni della chiave**, immettere **2048**
        
          - Confermare che il **nome del contenitore di chiavi automatico** sia selezionato
        
          - Lasciare deselezionate le altre caselle.
    
      - In **Opzioni aggiuntive** confermare i valori seguenti:
        
          - Per il **formato di richiesta** selezionare **CMC**.
        
          - Per l' **algoritmo hash** selezionare **SHA1**.
        
          - Per **nome descrittivo** immettere il **certificato Smardcard**.

8.  Se si utilizza un lettore di smartcard fisico, inserire la smart card nel dispositivo.

9.  Fare clic su **Invia** per inviare la richiesta di certificato.

10. Quando richiesto, immettere il PIN utilizzato per creare la smart card virtuale.
    
    <div>
    

    > [!NOTE]  
    > Il valore del PIN della smart card virtuale predefinito è' 12345678'.

    
    </div>

11. Dopo aver emesso il certificato, fare clic su **installa questo certificato** per completare il processo di registrazione.
    
    <div>
    

    > [!NOTE]  
    > Se la richiesta di certificato ha esito negativo con l'errore "questo Web browser non supporta la generazione di richieste di certificato", esistono tre modi possibili per risolvere il problema: 
    > <OL>
    > <LI>
    > <P>Abilitare la visualizzazione compatibilità in Internet Explorer</P>
    > <LI>
    > <P>Abilitare l'opzione attiva impostazioni Intranet in Internet Explorer</P>
    > <LI>
    > <P>Selezionare l'impostazione Reimposta tutte le aree sul livello predefinito nella scheda sicurezza nel menu opzioni di Internet Explorer.</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

