---
title: "Lync Server 2013: Configuring Enterprise CA per l'autenticazione con smart card"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abfbbb7a7f7787ab5490db1542c4435368a84ca0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532563"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Configurazione di CA dell'organizzazione per l'autenticazione con smart card in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-03_

Nella sezione seguente viene descritto come configurare un'autorità di certificazione (CA) radice dell'organizzazione per il supporto dell'autenticazione con smart card. Per informazioni su come installare una CA radice dell'organizzazione, vedere Install a Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) .

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurazione di un'autorità di certificazione radice dell'organizzazione per il supporto dell'autenticazione con smart card

Nella procedura seguente viene descritto come configurare una CA radice dell'organizzazione per il supporto dell'autenticazione con smart card:

1.  Accedere al computer della CA dell'organizzazione utilizzando un account di amministratore di dominio.

2.  Avviare System Manager e verificare che sia installato il ruolo di registrazione Web dell'autorità di certificazione.

3.  Dal menu **strumenti di amministrazione** , aprire la console di gestione **autorità di certificazione** .

4.  Nel riquadro di spostamento espandere **autorità di certificazione**.

5.  Fare clic con il pulsante destro del mouse su **modelli di certificato**, selezionare **nuovo**e quindi selezionare **modello di certificato da emettere**.

6.  Selezionare **l'agente di registrazione, l'** **utente smartcard**e l' **accesso smartcard**.

7.  Fare clic su **OK**.

8.  Fare clic con il pulsante destro su **modelli di certificato**.

9.  Selezionare **Gestisci**.

10. Aprire le proprietà del modello utente smartcard.

11. Fare clic sulla scheda **sicurezza** .

12. Modificare le autorizzazioni come indicato di seguito:
    
      - Aggiungere singoli account di Active Directory con autorizzazioni di lettura/registrazione (Consenti) oppure
    
      - Aggiungere un gruppo di sicurezza contenente gli utenti di smart card con autorizzazioni di lettura/registrazione (Consenti) oppure
    
      - Aggiungere il gruppo Domain Users con autorizzazioni di lettura/registrazione (Consenti)

</div>

</div>

<span> </span>

</div>

</div>

</div>

