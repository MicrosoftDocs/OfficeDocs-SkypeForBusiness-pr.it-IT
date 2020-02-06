---
title: Trasferire i dati dell'archivio file in un nuovo archivio di file in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Se è necessario rimuovere il file server che sta attualmente agendo come archivio di file per la distribuzione di Skype for Business Server 2015 o se è necessario apportare altre modifiche che rendessero disponibile il file Store corrente, è necessario prima di tutto creare una nuova condivisione. È quindi necessario eseguire la procedura seguente:'
ms.openlocfilehash: 7334246f4de6a820339e3fff5f9c19cb86a74422
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819518"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Trasferire i dati dell'archivio file in un nuovo archivio di file in Skype for Business Server 2015

Se è necessario rimuovere il file server che sta attualmente agendo come archivio di file per la distribuzione di Skype for Business Server 2015 o se è necessario apportare altre modifiche che rendessero disponibile il file Store corrente, è necessario prima di tutto creare una nuova condivisione. È quindi necessario eseguire la procedura seguente:

1. Arrestare i servizi di Skype for Business Server 2015 che usano l'archivio di file che si vuole rimuovere.

2. Definire l'archivio di file in Generatore di topologia e pubblicare le modifiche per rendere disponibile il nuovo archivio di file alla distribuzione.

3. Trasferire i dati nel nuovo archivio file.

4. Riavviare i server o i servizi.

5. Facoltativamente, rimuovere la vecchia condivisione di file e la cartella di file.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Per trasferire i dati dell'archivio file da un archivio file a un nuovo archivio file

1. Accedere a un computer come membro del gruppo RTCUniversersalServerAdmins o CsServerAdministrator in cui sono installati gli strumenti di amministrazione di Skype for Business Server 2015.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Nella barra di spostamento sinistra fare clic su **topologia**e quindi su **stato**.

4. Per ogni pool di Director, Director, server Standard Edition e pool Front end che usa l'archivio di file che si vuole rimuovere, selezionare il server o il pool, fare clic su **azione**e quindi su **Interrompi tutti i servizi**.

5. Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

6. Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi su **Skype for Business Server 2015Topology Builder**.

7. Selezionare un server o un pool che usa il file Store ed eseguire le operazioni seguenti:

8. Fare clic con il pulsante destro del mouse sul server o sul pool e quindi scegliere **modifica proprietà**.

9. In **proprietà modifica**, in **associazioni**, in **Archivio file**fare clic su **nuovo**.

10. In **Definisci nuovo archivio file**, in **FQDN file server**, digitare il nome di dominio completo (FQDN) del file server. In **condivisione file**Digitare il nome della cartella per la nuova condivisione file e quindi fare clic su **OK**.

     > [!IMPORTANT]
     > Questo passaggio definisce un nuovo archivio di file da usare in Generatore di topologie. Puoi definirla una sola volta, non per ogni server. Prima di pubblicare la topologia, è necessario creare la condivisione file definita nel file server definito. Per informazioni dettagliate, vedere [definire l'archivio di file per il front-end](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Per ogni server o pool che usa l'archivio di file, eseguire le operazioni seguenti:

12. Fare clic con il pulsante destro del mouse sul server o sul pool e quindi scegliere **modifica proprietà**.

13. In **proprietà modifica**, in **associazioni**, in **Archivio file**selezionare la nuova condivisione file e quindi fare clic su **OK**.

14. Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Skype for Business Server in base alle esigenze. Per informazioni dettagliate, vedere [procedure comuni per la rimozione di server e componenti Lync](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Avviare un prompt dei comandi: fare clic sul pulsante **Start**, scegliere **Esegui**e quindi digitare cmd. exe.

16. Nella riga di comando digitare quanto segue:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > L'opzione/S copia i file, le directory e le sottodirectory. L'opzione/XF ignora tutti i file denominati meeting. Active. Le versioni correnti di Robocopy. exe con l'opzione/MT aumentano notevolmente la velocità di copia usando più thread. Per l'opzione/LOG, usare un percorso di directory e un nome di file di log sotto forma di C:\Logfiles\log.txt. Questa opzione consente di creare un file di log delle operazioni nella posizione denominata.

17. Al termine della copia dei dati, nel pannello di controllo di Lync Server fare clic su **topologia**e quindi su **stato**.

18. Per ogni server o pool in cui sono stati arrestati i servizi, selezionare il server o il pool, fare clic su **azione**e quindi su **Avvia tutti i servizi**.

19. Rimuovere il vecchio archivio di file dalla topologia e quindi pubblicare la topologia. Per informazioni dettagliate, vedere [rimuovere un archivio di file](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. Opzionale Accedere al computer che contiene l'archivio di file appena rimosso come membro del gruppo Administrators locale o del gruppo Domain Admins e quindi rimuovere la vecchia condivisione file e la directory.

## <a name="see-also"></a>Vedere anche

[Riassegnare un server a un altro archivio di file](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Rimuovere un archivio di file](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
