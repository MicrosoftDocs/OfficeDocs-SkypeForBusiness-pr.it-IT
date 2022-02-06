---
title: Configurazione delle notifiche Push del client mobile
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Per configurare le Notifiche Push di Microsoft e le Notifiche Push di Apple, è necessario creare un criterio per definire quali tipi di notifiche push sono necessari.'
---

# <a name="mobile-client-push-notification-configuration"></a>Client dispositivo mobile: configurazione di notifiche push
 
Per configurare le **Notifiche Push di Microsoft** e le **Notifiche Push di Apple**, è necessario creare un criterio per definire quali tipi di notifiche push sono necessari.
  
Nella schermata di configurazione principale è possibile fare clic su **Aggiorna** per aggiornare e popolare di nuovo l'elenco di criteri. È disponibile una casella di ricerca per limitare l'elenco di criteri visualizzati. Man mano che si digita il nome da cercare, l'elenco di criteri si restringe automaticamente.
  
> [!IMPORTANT]
> Le impostazioni criteri applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri è: i criteri utente (la maggiore influenza) hanno la precedenza su un criterio sito e quindi un criterio sito sostituisce un criterio globale (meno influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto. 
  
Sono disponibili due selezioni per la creazione e la modifica dei criteri:
  
1. **Nuovo**: fare clic su questa opzione per creare un nuovo criterio. È necessario fornire un sito a cui applicare il criterio e quindi configurare le impostazioni per le notifiche push. Per **Configurazione notifica Push** è possibile creare criteri solo per i siti già creati.
    
2. **Modifica**: selezionare un criterio e fare clic su Modifica per selezionare un'azione dal menu a discesa. È possibile modificare solo i siti già creati o modificare il criterio Globale.
    
   - **Mostra dettagli…**: mostra informazioni sul criterio attualmente selezionato. È possibile modificare solo il criterio esistente.
    
   - **Seleziona tutto**: se sono disponibili alcuni criteri ed è necessario selezionarli tutti, fare clic su Seleziona tutto.
    
   - **Elimina**: rimuove il criterio selezionato. Usando **Seleziona tutto** ed **Elimina** si rimuoveranno tutti i criteri.
    
     > [!NOTE]
     > Non è invece possibile eliminare il criterio **Globale**. Se si tenta di eliminarlo, verrà segnalato che tale criterio è stato ripristinato ai valori predefiniti (ovvero tutte le impostazioni sono state cancellate), ma non può essere rimosso.
  
La creazione di un nuovo criterio o la modifica di un criterio esistente sono associate a due azioni:
  
- **Commit** L'azione di commit crea o aggiorna il criterio e salva le modifiche
    
- **Annulla** L'azione Annulla elimina tutte le modifiche apportate dopo l'ultima azione di commit. Se si sceglie di annullare, tutte le modifiche eseguite andranno perse.
    
Sono possibili due impostazioni per **Configurazione notifica Push** che sono associate ai servizi di notifica Push per Microsoft e per Apple. Per abilitare la notifica Push per questi servizi, selezionare la casella di controllo accanto al nome del servizio. È possibile deselezionare la casella di controllo facendo clic su di essa. Dopo aver eseguito le selezioni, eseguire il commit o annullare. Facendo clic su Commit si salveranno le modifiche al criterio.
  

