---
title: Configurare l'utilizzo di foto ad alta risoluzione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: "Riepilogo: configurare l'utilizzo di foto ad alta risoluzione in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online e Skype for Business Server."
ms.openlocfilehash: c55e5a90e222ea024dd63f72b26627141b2f113e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834006"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurare l'utilizzo di foto ad alta risoluzione in Skype for Business Server
 
**Riepilogo:** Configurare l'utilizzo di foto ad alta risoluzione in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online e Skype for Business Server.
  
In Skype for Business Server, le foto possono essere archiviate in una cassetta postale di Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online, che consente di ridimensionare le foto fino a 648 pixel per 648 pixel. Inoltre, Exchange Server può ridimensionare automaticamente queste foto per l'utilizzo in prodotti diversi in base alle esigenze. Questo significa in genere tre diverse dimensioni e risoluzioni delle Foto:
  
- 64 pixel per 64 pixel, la dimensione utilizzata per l'attributo thumbnailPhoto di Active Directory. Se si carica una foto su Exchange Server, Exchange creerà automaticamente una versione in pixel di 64 pixel per 64 di quella foto e aggiornerà l'attributo thumbnailPhoto dell'utente. Si noti, tuttavia, che l'inverso non è vero: se si aggiorna manualmente l'attributo thumbnailPhoto in Active Directory, la foto nella cassetta postale di Exchange dell'utente non verrà aggiornata automaticamente.
    
- 96 pixel per 96 pixel, per l'utilizzo in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App e Skype for business.
    
- 648 pixel per 648 pixel per l'utilizzo in Skype for business e Skype for business web app Skype for Business Web App.
    
> [!NOTE]
> Se si dispone delle risorse, si consiglia di caricare 648 x 648 foto; che fornisce la risoluzione massima e la qualità ottimale delle immagini in tutte le applicazioni di Office 2013. Ogni foto JPEG con una dimensione di 648 x 648 e una profondità di 24 bit genera una dimensione di un file di circa 240 kilobyte. Ciò significa che sarà necessario circa 1 megabyte di spazio su disco per ogni 4 foto di utenti. 
  
Le foto ad alta risoluzione, a cui si accede utilizzando servizi Web Exchange, possono essere caricate dagli utenti che eseguono Outlook 2013 Web App. Gli utenti possono solo aggiornare la propria foto. Gli amministratori, tuttavia, possono aggiornare la foto per qualsiasi utente utilizzando Exchange Management Shell e una serie di comandi di Windows PowerShell simili ai seguenti:
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Il primo comando nell'esempio precedente utilizza il `Get-Content` cmdlet per leggere il contenuto del file C:\Photos\Kenmyer.jpg e archiviare i dati in una variabile denominata $Photo. Nel secondo comando viene utilizzato il cmdlet Exchange `Set-UserPhoto` per caricare la foto e allegarla all'account utente di Ken.
  
> [!NOTE]
> In questo esempio, il nome visualizzato di Active Directory di Ken Myer è utilizzato come identità dell'account utente. È anche possibile fare riferimento a un account utente mediante altri identificatori quali l'indirizzo SMTP dell'utente oppure il relativo nome dell'entità utente. Per ulteriori informazioni, vedere la documentazione relativa al cmdlet Set-UserPhoto. [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)
  
Il caricamento della foto non equivale ad assegnarla all'account utente di Ken Myer. Esso infatti produce semplicemente un'anteprima della foto da visualizzare nella pagina Opzioni di Outlook Web App. Per assegnare effettivamente la foto all'account utente, quest'ultimo deve fare clic su **Salva** nella pagina Opzioni oppure l'amministratore deve eseguire il terzo comando nell'esempio. Il terzo comando usa il parametro Save per assegnare la foto all'account utente di Ken Myer:
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Per verificare che la nuova foto sia stata assegnata all'account utente, Ken è in grado di accedere a Skype for business, selezionare **Opzioni** e quindi fare clic su **immagine personale**. La nuova foto aggiunta deve essere visualizzata come foto personale di Ken. In alternativa, gli amministratori possono verificare la foto per qualsiasi utenti avviando Internet Explorer e passando a un URL analogo a questo:
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

Se l'amministratore può visualizzare la foto utilizzando Internet Explorer, ma l'utente non può visualizzare la propria foto in Skype for business, potrebbe verificarsi un problema di connettività con i servizi Web di Exchange o con il servizio di individuazione automatica di Exchange.
  
Si noti che non è necessaria alcuna configurazione aggiuntiva per rendere questa foto disponibile in Skype for business. Al contrario, la foto sarà immediatamente disponibile dopo che è stata caricata e il `Set-UserPhoto` cmdlet è stato eseguito.
