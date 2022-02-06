---
title: Configurare l'uso di foto ad alta risoluzione in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Riepilogo: configurare l''utilizzo di foto ad alta risoluzione in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online e Skype for Business Server.'
---

# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Configurare l'uso di foto ad alta risoluzione in Skype for Business Server
 
**Riepilogo:** Configurare l'uso di foto ad alta risoluzione in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online e Skype for Business Server.
  
In Skype for Business Server, le foto possono essere archiviate nella cassetta postale di Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online, che consente dimensioni delle foto fino a 648 pixel per 648 pixel. Inoltre, Exchange Server ridimensionare automaticamente queste foto per l'uso in prodotti diversi in base alle esigenze. Questo significa in genere tre diverse dimensioni e risoluzioni delle foto:
  
- 64 pixel per 64 pixel, le dimensioni usate per l'attributo thumbnailPhoto di Active Directory. Se carichi una foto in Exchange Server, Exchange creerà automaticamente una versione di 64 pixel per 64 pixel di tale foto e aggiornerà l'attributo thumbnailPhoto dell'utente. Si noti, tuttavia, che il contrario non è vero: se si aggiorna manualmente l'attributo thumbnailPhoto in Active Directory, la foto nella cassetta postale Exchange dell'utente non verrà aggiornata automaticamente.
    
- 96 pixel per 96 pixel, da usare in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App e Skype for Business.
    
- 648 pixel per 648 pixel da usare in Skype for Business e Skype for Business Web App Skype for Business Web App.
    
> [!NOTE]
> Se si dispone delle risorse, è consigliabile caricare foto 648 x 648; che fornisce la risoluzione massima e la qualità ottimale dell'immagine in una qualsiasi delle applicazioni Office 2013. Ogni foto JPEG con una dimensione di 648 x 648 e una profondità di 24 bit determina una dimensione del file di circa 240 kilobyte. Ciò significa che sarà necessario circa 1 megabyte di spazio su disco per ogni 4 foto di utenti. 
  
Le foto ad alta risoluzione, a cui si accede tramite servizi Web Exchange, possono essere caricate dagli utenti che eseguono Outlook Web App 2013; gli utenti possono solo aggiornare le proprie foto. Gli amministratori, tuttavia, possono aggiornare la foto per qualsiasi utente utilizzando Exchange Management Shell e una serie di comandi Windows PowerShell simili ai seguenti:
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Nel primo comando dell'esempio `Get-Content` precedente viene utilizzato il cmdlet per leggere il contenuto del file C:\Photos\Kenmyer.jpg e archiviare tali dati in una variabile denominata $photo. Nel secondo comando viene utilizzato il cmdlet `Set-UserPhoto` Exchange per caricare la foto e allegare la foto all'account utente di Ken Myer.
  
> [!NOTE]
> In questo esempio, il nome visualizzato di Active Directory di Ken Myer è utilizzato come identità dell'account utente. È anche possibile fare riferimento a un account utente mediante altri identificatori quali l'indirizzo SMTP dell'utente oppure il relativo nome dell'entità utente. Per ulteriori informazioni, vedere la documentazione Set-UserPhoto cmdlet di [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto) configurazione
  
Il caricamento della foto non equivale ad assegnarla all'account utente di Ken Myer. Esso infatti produce semplicemente un'anteprima della foto da visualizzare nella pagina Opzioni di Outlook Web App. Per assegnare effettivamente la foto all'account utente, quest'ultimo deve fare clic su **Salva** nella pagina Opzioni oppure l'amministratore deve eseguire il terzo comando nell'esempio. Il terzo comando usa il parametro Save per assegnare la foto all'account utente di Ken Myer:
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Per verificare che la nuova foto sia stata assegnata all'account utente, Ken Myer può accedere a Skype for Business, selezionare **Opzioni e quindi** **Selezionare Immagine personale**. La nuova foto aggiunta deve essere visualizzata come foto personale di Ken. In alternativa, gli amministratori possono verificare la foto per qualsiasi utenti avviando Internet Explorer e passando a un URL analogo a questo:
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

Se l'amministratore può visualizzare la foto utilizzando Internet Explorer, ma l'utente non può visualizzare la propria foto in Skype for Business potrebbe verificarsi un problema di connettività con i servizi Web di Exchange o con il servizio di individuazione automatica di Exchange.
  
Nota anche che non è necessaria alcuna configurazione aggiuntiva per rendere disponibile questa foto in Skype for Business. Al contrario, la foto sarà immediatamente disponibile dopo il caricamento e l'esecuzione `Set-UserPhoto` del cmdlet.