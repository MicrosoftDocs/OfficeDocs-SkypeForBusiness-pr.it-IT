---
title: 'Lync Server 2013: attivazione della connettività Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bb14153739c5f29e88044eae89a1322b046a0a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Abilitazione della connettività Lync-Skype in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-12-16_

Dopo aver inoltrato la richiesta di provisioning, è possibile concentrarsi sull'ambiente Lync Server e sulle attività amministrative necessarie per configurare la connettività Lync-Skype. In questa sezione si presuppone che l'amministratore di Lync Server abbia distribuito Lync Server e abbia configurato l'accesso esterno. Per ulteriori informazioni sulla configurazione dell'accesso esterno per Lync Server, vedere [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Per preparare l'ambiente Lync Server per la connettività Lync-Skype, è necessario che l'amministratore di Lync Server completi le tre attività seguenti:

<div>

## <a name="1-configure-federation-and-pic"></a>1\. Configurazione della Federazione e del PIC

La Federazione è necessaria per consentire agli utenti di Skype di comunicare con gli utenti di Lync nell'organizzazione. La connettività per la messaggistica istantanea pubblica (PIC) è una classe di Federazione e deve essere configurata per consentire agli utenti di Lync di comunicare con gli utenti di Skype. La Federazione e il PIC sono configurati utilizzando il pannello di controllo di Lync Server, mostrato di seguito.

![Visualizzazione PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Visualizzazione PIC")

<div>


> [!IMPORTANT]  
> La Federazione PIC non è più supportata da Live Communication Server 2005 SP1 o da Office Communications Server 2007. Le piattaforme supportate per la Federazione PIC sono Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. Configurare almeno un criterio per il supporto dell'accesso utente federato

Se si utilizza il pannello di controllo di Lync Server, un amministratore deve configurare uno o più criteri di accesso utente esterno per controllare se gli utenti di Skype possono collaborare con gli utenti interni di Lync Server.

![Generali](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Generali")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Configurare l'impostazione di Skype PIC provider per Lync

Utilizzando Lync Server Management Shell, un amministratore deve configurare il criterio client di Lync per visualizzare Skype come un ulteriore provider PIC.

<div>


> [!NOTE]  
> Gli utenti dei provider di servizi di connettività di messaggistica istantanea pubblica non possono partecipare a conferenze di messaggistica istantanea o audio o video nell'organizzazione fino a quando non si configura anche almeno un criterio (passaggio 2, più indietro in questa procedura) per supportare la connettività di messaggistica istantanea pubblica.



</div>

1.  Per configurare la Federazione e il PIC, vedere "abilitare o disabilitare la Federazione e la connettività [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063)per la messaggistica istantanea pubblica" all'indirizzo.

2.  Per configurare almeno un criterio per il supporto dell'accesso degli utenti federati, vedere la sezione relativa alla configurazione di criteri per [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064)il controllo dell'accesso degli utenti pubblici all'indirizzo.

**Per modificare un provider di Messenger o Skype PIC esistente e configurarlo per Skype**

1.  Da un server front-end di Lync Server, aprire Lync Server Management Shell.

2.  Eseguire i due comandi seguenti:
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > Se non si dispone già di un provider PIC nel proprio ambiente e si crea un nuovo provider PIC, non è necessario eseguire il cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > Aggiunta in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, NameDecorationRoutingDomain e NameDecorationExcludedDomainList migliorano la situazione in cui gli utenti di Lync aggiungono contatti Skype necessari per "decorare" i domini non Microsoft per identificare e instradarli a Skype (il formato di: User (contoso. com) @msn. com). Queste nuove impostazioni consentiranno la formattazione automatica della finestra di dialogo "Aggiungi contatto Skype" con il NameDecorationRoutingDomain (che dovrebbe essere impostato su msn.com) se non contiene i domini in NameDecorationExcludedDomainList ( Attualmente è in grado di supportare msn.com, live.com, Hotmail.com, outlook.com).

    
    </div>

3.  Da un client Lync, è ora possibile selezionare Skype come provider PIC e aggiungere un client Skype specificando il proprio account Microsoft. Inoltre, un utente Skype che ha eseguito l'Unione e l'accesso con il proprio account Microsoft può inviare una richiesta di contatto agli utenti di Lync. Per ulteriori informazioni sugli account Microsoft, vedere [che cos'è un account Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Per ulteriori informazioni sull'aggiunta di client a Lync, vedere [utilizzo della connettività Lync-Skype in Lync Server 2013 come utente finale](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Aggiungere contatti Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Aggiungere contatti Skype")

4.  Per informazioni dettagliate sulla modifica dei provider ospitati, vedere "creare o modificare provider federati SIP ospitati" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).

Vengono completate le attività amministrative che devono essere eseguite sul server. È ora configurato per la connettività Lync-Skype.

</div>

</div>

<span> </span>

</div>

</div>

</div>

