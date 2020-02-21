---
title: "Lync Server 2013: configurazione dell'utilizzo di foto ad alta risoluzione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a49618cd4039163f22d44f358c29a802037b8b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Configurazione dell'utilizzo di foto ad alta risoluzione in Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

Microsoft Lync Server 2010 ha offerto agli utenti la possibilità di visualizzare le foto dei propri contatti (e di rendere disponibili le proprie foto ad altri). In genere, queste foto vengono archiviate come parte dell'attributo thumbnailPhoto dell'utente in Active Directory. Ciò implica una seria limitazione alle dimensioni e alle risoluzioni delle foto: l'attributo thumbnailPhoto può contenere solo una fotografia di dimensioni massime pari a 48x48 pixel.

In Microsoft Lync Server 2013, tuttavia, le foto possono essere archiviate in una cassetta postale di Microsoft Exchange Server 2013 dell'utente. che consente di ridimensionare le foto fino a 648 pixel per 648 pixel. Inoltre, Exchange 2013 può ridimensionare automaticamente queste foto per l'utilizzo in prodotti diversi in base alle esigenze. Questo significa in genere tre diverse dimensioni e risoluzioni delle Foto:

  - 48x48 pixel, le dimensioni usate per l'attributo thumbnailPhoto di Active Directory. Se si carica una foto su Exchange 2013 Exchange creerà automaticamente una versione a 48 pixel per 48 pixel di quella foto e aggiornerà l'attributo thumbnailPhoto dell'utente. Si noti, tuttavia, che l'inverso non è vero: se si aggiorna manualmente l'attributo thumbnailPhoto in Active Directory, la foto nella cassetta postale di Exchange 2013 dell'utente non verrà aggiornata automaticamente.

  - 96 pixel per 96 pixel, per l'utilizzo in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App e Lync 2013.

  - 648 pixel per 648 pixel per l'utilizzo in Lync 2013 e Microsoft Lync Web App.

<div>


> [!NOTE]  
> Se si dispone delle risorse, è consigliabile caricare foto nel formato 648x648 che offrono la risoluzione massima e la qualità ottimale dell'immagine in qualsiasi applicazione di Office 2013. Ogni foto JPEG di dimensioni pari a 648x648 e una profondità di 24 bit produce un file di dimensioni pari a circa 240 kilobyte. Ciò significa che sarà necessario circa 1 megabyte di spazio su disco per ogni 4 foto di utenti.



</div>

Le foto ad alta risoluzione, a cui si accede utilizzando servizi Web Exchange, possono essere caricate dagli utenti che eseguono Outlook 2013 Web App. Gli utenti possono solo aggiornare la propria foto. Gli amministratori, tuttavia, possono aggiornare la foto per qualsiasi utente utilizzando Exchange Management Shell e una serie di comandi di Windows PowerShell simili ai seguenti:

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Il primo comando nell'esempio precedente utilizza il cmdlet Get-Content per leggere il contenuto del file C:\\Photos\\kenmyer. jpg e archiviare i dati in una variabile denominata $Photo. Nel secondo comando viene utilizzato il cmdlet Set-UserPhoto di Exchange per caricare la foto e allegarla all'account utente di Ken.

<div>


> [!NOTE]  
> In questo esempio, il nome visualizzato di Active Directory di Ken Myer è utilizzato come identità dell'account utente. È anche possibile fare riferimento a un account utente mediante altri identificatori quali l'indirizzo SMTP dell'utente oppure il relativo nome dell'entità utente. <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> Per ulteriori informazioni, vedere la documentazione relativa al cmdlet Set-UserPhoto.



</div>

Il caricamento della foto non equivale ad assegnarla all'account utente di Ken Myer. Esso infatti produce semplicemente un'anteprima della foto da visualizzare nella pagina Opzioni di Outlook Web App. Per assegnare effettivamente la foto all'account utente, quest'ultimo deve fare clic su **Salva** nella pagina Opzioni oppure l'amministratore deve eseguire il terzo comando nell'esempio. Il terzo comando usa il parametro Save per assegnare la foto all'account utente di Ken Myer:

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Per verificare che la nuova foto sia stata assegnata all'account utente, Ken è in grado di accedere a Lync 2013, selezionare **Opzioni**e quindi selezionare **immagine personale**. La nuova foto aggiunta deve essere visualizzata come foto personale di Ken. In alternativa, gli amministratori possono verificare la foto per qualsiasi utenti avviando Internet Explorer e passando a un URL analogo a questo:

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

Se l'amministratore può visualizzare la foto utilizzando Internet Explorer, ma l'utente non è in grado di visualizzare la propria foto in Lync 2013, indica in genere un problema di connettività con i servizi Web di Exchange o con il servizio di individuazione automatica di Exchange.

Si noti, inoltre, che non è necessaria alcuna configurazione aggiuntiva per rendere questa foto disponibile in Lync 2013. Al contrario, la foto sarà immediatamente disponibile dopo che è stata caricata e il cmdlet Set-UserPhoto è stato eseguito.

</div>

<span> </span>

</div>

</div>

</div>

