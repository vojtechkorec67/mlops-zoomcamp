# mlops-zoomcamp

## Připojení k Google Cloud VM

Pokud chcete přistupovat ke své instanci Compute Engine v Google Cloud, použijte následující kroky.

1. Přihlaste se do Google Cloud CLI:
   ```bash
   gcloud auth login
   ```

2. Nastavte projekt:
   ```bash
   gcloud config set project YOUR_PROJECT_ID
   ```

3. Připojte se k instanci:
   ```bash
   gcloud compute ssh YOUR_INSTANCE_NAME --zone=YOUR_ZONE --project=YOUR_PROJECT_ID
   ```

4. Pokud chcete připojit přes webové rozhraní, otevřete Google Cloud Console, přejděte na Compute Engine -> VM instances a klikněte na SSH u své instance.

5. Místní hodnoty, které si chcete uchovat jen lokálně, uložte do souboru cloud-config.env a nepřidávejte ho do git:
   ```bash
   export PROJECT_ID="YOUR_PROJECT_ID"
   export INSTANCE_NAME="YOUR_INSTANCE_NAME"
   export ZONE="YOUR_ZONE"
   ```
   Poté je můžete načíst:
   ```bash
   source cloud-config.env
   ```

> Pokud gcloud vytváří SSH klíč poprvé, stačí potvrdit výchozí hodnoty stiskem Enter.
