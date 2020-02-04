---
title: "Lync Server 2013: registrazione degli utenti per l'autenticazione tramite smart card"
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
ms.openlocfilehash: 750e77b342b48d2c81bf05e160779ca5566f5a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Registrazione degli utenti per l'autenticazione tramite smart card in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-03_

Sono in genere disponibili due metodi per l'iscrizione degli utenti per l'autenticazione tramite smart card. Il metodo più semplice consiste nel fatto che gli utenti si iscrivono direttamente per l'autenticazione con smart card usando la registrazione Web, mentre il metodo più complesso prevede l'uso di un agente di registrazione. Questo argomento riguarda l'autoregistrazione per i certificati smartcard.

Per altre informazioni sull'iscrizione per conto degli utenti come agente di registrazione, vedere registrare i certificati per conto di altri utenti [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>Per registrare gli utenti per l'autenticazione tramite smart card

1.  Accedere alla workstation Windows 8 usando le credenziali di un utente abilitato per Lync.

2.  Avviare Internet Explorer.

3.  Passare alla pagina di **registrazione Web Authority Certificate** (ad esempio https://MyCA.contoso.com/certsrv).
    
    <div>
    

    > [!NOTE]  
    > Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare il sito Web in modalità compatibilità.

    
    </div>

4.  Nella pagina di **benvenuto** selezionare **Richiedi un certificato**.

5.  Selezionare quindi **Advanced request**.

6.  Selezionare **Crea e invia una richiesta a questa CA**.

7.  Selezionare **utente smartcard** nella sezione **modello di certificato** e completare la richiesta di certificato avanzato con i valori seguenti:
    
      - Le **Opzioni principali** confermano le impostazioni seguenti:
        
          - Selezionare il pulsante di opzione **Crea nuovo set di tasti**
        
          - Per **CSP**selezionare **provider di crittografia Smart Card Microsoft base**
        
          - Per l' **utilizzo delle chiavi**, selezionare **Exchange** (questa è l'unica opzione disponibile).
        
          - Per le **dimensioni della chiave**, immettere **2048**
        
          - Verificare che il **nome del contenitore di tasti automatico** sia selezionato
        
          - Abbandonare le altre caselle deselezionate.
    
      - In **Opzioni aggiuntive** confermare i valori seguenti:
        
          - Per il **formato di richiesta** selezionare **CMC**.
        
          - Per l' **algoritmo hash** selezionare **SHA1**.
        
          - Per **nome descrittivo** immettere il **certificato Smardcard**.

8.  Se si usa un lettore di smartcard fisico, inserire la smart card nel dispositivo.

9.  Fare clic su **Invia** per inviare la richiesta di certificato.

10. Quando richiesto, immettere il PIN usato per creare la smart card virtuale.
    
    <div>
    

    > [!NOTE]  
    > Il valore PIN della smart card virtuale predefinito è "12345678".

    
    </div>

11. Dopo aver emesso il certificato, fare clic su **installa questo certificato** per completare il processo di registrazione.
    
    <div>
    

    > [!NOTE]  
    > Se la richiesta di certificato non riesce con l'errore "questo Web browser non supporta la generazione di richieste di certificato," Esistono tre modi possibili per risolvere il problema: 
    > <OL>
    > <LI>
    > <P>Abilitare la visualizzazione compatibilità in Internet Explorer</P>
    > <LI>
    > <P>Abilitare l'opzione attiva impostazioni Intranet in Internet Explorer</P>
    > <LI>
    > <P>Selezionare l'impostazione Reimposta tutte le aree su livello predefinito nella scheda sicurezza del menu opzioni di Internet Explorer.</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

