---
title: 'Lync Server 2013: creare o modificare un intervallo di numeri non assegnati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90b6068de77a1a32f45afbc34604dc70a4daf58e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Creare o modificare un intervallo di numeri non assegnati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Usare una delle procedure seguenti per configurare gli intervalli di numeri non assegnati per l'applicazione di annuncio.

<div>


> [!IMPORTANT]  
> Prima di configurare la tabella dei numeri non assegnati, è necessario avere già definito uno o più annunci o configurare un operatore automatico di messaggistica UNIFICAta di Exchange.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>Per usare il pannello di controllo di Lync Server per configurare i numeri di telefono non assegnati

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **caratteristiche vocali**e quindi su **numero non assegnato**.

4.  Nella pagina **numero non assegnati** eseguire una delle operazioni seguenti:
    
      - Per creare un nuovo intervallo di numeri, fare clic su **nuovo**. In **nome**Digitare un nome identificativo per l'intervallo di numeri.
        
        <div>
        

        > [!NOTE]  
        > Dopo aver eseguito il commit del nuovo intervallo di numeri non assegnati al database, non è possibile modificare questo nome.

        
        </div>
    
      - Per modificare un intervallo di numeri esistente, digitare tutto o parte del nome dell'intervallo di numeri nel campo di ricerca. Nell'elenco di intervalli di numeri risultante fare clic sul nome desiderato, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Nel campo primo **intervallo di numeri** Digitare il numero iniziale dell'intervallo, quindi digitare il numero finale dell'intervallo nel secondo campo **intervallo di numeri** .
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</P>
    > <LI>
    > <P>Se il numero di inizio dell'intervallo o il numero finale dell'intervallo include un numero di interno, sia il numero iniziale che il numero finale dell'intervallo devono includere un'estensione e il numero di interno deve essere uguale sia per il numero iniziale che per il numero finale.</P>
    > <LI>
    > <P>Il numero deve corrispondere all'espressione regolare (Tel:)? \+)? [1-9] \d{0,17}(; EXT = [1-9] \d{0,9})?. Questo significa che il numero può iniziare con la stringa tel: (se non specifichi quella stringa, verrà automaticamente aggiunta per te), un segno più (+) e una cifra da 1 a 9. Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.</P></LI></UL>

    
    </div>

6.  In **servizio annunci**eseguire una delle operazioni seguenti:
    
      - Fare clic su **annuncio**.
    
      - Fare clic su **messaggistica unificata di Exchange**.

7.  Se nel passaggio precedente è stato fatto clic su **annuncio**, eseguire le operazioni seguenti:
    
    1.  In **FQDN del server di destinazione**, fare clic su **Seleziona**, fare clic sull'ID servizio del servizio applicazione che esegue l'applicazione di annuncio che gestirà le chiamate in arrivo in questo intervallo di numeri non assegnati e quindi fare clic su **OK**.
    
    2.  In **annuncio**fare clic sull'annuncio da riprodurre per l'intervallo di numeri non assegnati.

8.  Se nel passaggio precedente è stato fatto clic su **um Exchange**, in **numero di telefono operatore automatico**fare clic su **Seleziona**, fare clic sul numero di telefono da usare per l'intervallo di numeri non assegnati e quindi fare clic su **OK**.

9.  Fare clic su **OK**.

10. Nella pagina **numero non assegnati** verificare che gli intervalli di numeri non assegnati siano disposti nell'ordine desiderato. Per modificare la posizione di un intervallo nella tabella, fare clic su uno o più nomi consecutivi nell'elenco di intervalli e quindi fare clic sulla freccia su o freccia giù.
    
    <div>
    

    > [!TIP]  
    > Lync Server cerca nella tabella numeri non assegnati dall'alto verso il basso e usa il primo intervallo che corrisponde al numero non assegnato. Se si hanno intervalli sovrapposti e un intervallo specifica un'ultima azione di ricorso, verificare che l'intervallo sia nella parte inferiore dell'elenco.

    
    </div>

11. Quando si hanno gli intervalli di numeri non assegnati nell'ordine desiderato, fare clic su **commit tutti**.

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>Per usare Windows PowerShell per configurare i numeri di telefono non assegnati

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  USA **New-CsUnassignedNumber** per creare un nuovo intervallo di numeri non assegnati. Usare **Set-CsUnassignedNumber** per modificare un intervallo di numeri non assegnati esistente.
    
    <div>
    

    > [!TIP]  
    > Se si hanno intervalli sovrapposti e si vogliono applicare gli intervalli in un ordine specifico, includere il parametro Priority. L'intervallo con la priorità più alta verrà applicato alla chiamata.

    
    </div>
    
    Nella riga di comando eseguire una delle operazioni seguenti:
    
      - Per creare un intervallo di numeri per un servizio di annuncio, eseguire:
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - In alternativa, per creare un intervallo di numeri per l'operatore automatico di messaggistica unificata di Exchange, eseguire:
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    Ad esempio:
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    O
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    L'esempio seguente mostra come modificare i numeri in un intervallo di numeri non assegnati esistente:
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminare un intervallo di numeri non assegnati in Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

