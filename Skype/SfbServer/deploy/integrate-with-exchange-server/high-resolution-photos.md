---
title: Configurare l'uso di foto ad alta risoluzione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: "Riepilogo: configurare l'uso di foto ad alta risoluzione in Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server."
ms.openlocfilehash: d52cdb2d84fedba0dcbec97cbca4074b1ae12a84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188144"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurare l'uso di foto ad alta risoluzione in Skype for Business Server
 
**Riepilogo:** Configurare l'uso di foto ad alta risoluzione in Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.
  
In Skype for Business Server le foto possono essere archiviate in una cassetta postale di Exchange Server 2016 o Exchange Server 2013 di un utente, che consente di ridimensionare le foto fino a 648 pixel per 648 pixel. Inoltre, Exchange Server può ridimensionare automaticamente queste foto per l'uso in prodotti diversi in base alle esigenze. In genere significa tre diverse dimensioni e risoluzioni delle Foto:
  
- 64 pixel per 64 pixel, le dimensioni usate per l'attributo thumbnailPhoto di Active Directory. Se si carica una foto in Exchange Server, Exchange creerà automaticamente una versione di 64 pixel per 64 pixel della foto e aggiornerà l'attributo thumbnailPhoto dell'utente. Si noti tuttavia che il contrario non è vero: se si aggiorna manualmente l'attributo thumbnailPhoto in Active Directory, la foto nella cassetta postale di Exchange dell'utente non verrà aggiornata automaticamente.
    
- 96 pixel per 96 pixel, per l'uso in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App e Skype for business.
    
- 648 pixel per 648 pixel per l'uso in Skype for business e Skype for business web app Skype for Business Web App.
    
> [!NOTE]
> Se si hanno le risorse, è consigliabile caricare le foto di 648 x 648; che offre la massima risoluzione e una qualità ottimale delle immagini in tutte le applicazioni di Office 2013. Ogni foto JPEG con una dimensione di 648 x 648 e una profondità di 24 bit genera una dimensione del file di circa 240 kilobyte. Questo significa che avrai bisogno di circa 1 megabyte di spazio su disco per ogni 4 foto utente. 
  
Le foto ad alta risoluzione, a cui si accede usando i servizi Web di Exchange, possono essere caricate dagli utenti che usano Outlook 2013 Web App; agli utenti è consentito aggiornare solo la propria foto. Gli amministratori possono tuttavia aggiornare la foto per qualsiasi utente usando Exchange Management Shell e una serie di comandi di Windows PowerShell simili ai seguenti:
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Il primo comando nell'esempio precedente usa il `Get-Content` cmdlet per leggere il contenuto del file C:\Photos\Kenmyer.jpg e archiviare i dati in una variabile denominata $Photo. Nel secondo comando viene usato il cmdlet `Set-UserPhoto` Exchange per caricare la foto e allegare la foto all'account utente di Ken.
  
> [!NOTE]
> In questo esempio, il nome visualizzato in Active Directory di Ken è usato come identità dell'account utente. È anche possibile fare riferimento a un account utente usando altri identificatori, ad esempio l'indirizzo SMTP dell'utente o il nome dell'entità utente. [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) Per altre informazioni, vedere la documentazione relativa al cmdlet Set-UserPhoto.
  
Il caricamento della foto non equivale all'assegnazione di tale foto all'account utente di Ken. Invece, il caricamento della foto restituisce semplicemente un'anteprima della foto da visualizzare nella pagina delle opzioni di Outlook Web App. Per assegnare effettivamente la foto all'account utente, l'utente deve fare clic su **Salva** nella pagina Opzioni oppure l'amministratore deve eseguire il terzo comando nell'esempio. Questo terzo comando usa il parametro Save per assegnare la foto all'account utente di Ken requestro:
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Per verificare che la nuova foto sia stata assegnata all'account utente, Ken può accedere a Skype for business, selezionare **Opzioni**e quindi selezionare **immagine personale**. La foto appena caricata deve essere visualizzata come foto personale di Ken. In alternativa, gli amministratori possono verificare la foto per qualsiasi utente avviando Internet Explorer e passando a un URL simile al seguente:
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

Se l'amministratore può visualizzare la foto usando Internet Explorer, ma l'utente non può visualizzare la propria foto in Skype for business, potrebbe trattarsi di un problema di connettività con i servizi Web di Exchange o con il servizio di individuazione automatica di Exchange.
  
Tieni presente che non è necessaria alcuna configurazione aggiuntiva per rendere disponibile questa foto in Skype for business. La foto verrà invece immediatamente resa disponibile dopo il caricamento e il `Set-UserPhoto` cmdlet sarà stato eseguito.
