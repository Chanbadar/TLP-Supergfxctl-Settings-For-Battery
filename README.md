# TLP ve Supergfxctl Batarya Ayarları

Bu rehber, NVIDIA ekran kartına sahip dizüstü bilgisayarlarda batarya ömrünü artırmak için TLP ve Supergfxctl kullanımını anlatmaktadır.

## TLP Kurulumu

TLP paketini kurun:

```bash
sudo pacman -S tlp
```

TLP servisinin sistem açılışında otomatik başlamasını sağlayın:

```bash
sudo systemctl enable tlp.service
```

TLP'yi hemen başlatın:

```bash
sudo tlp start
```
## TLP Yapılandırması

Depodaki `tlp.conf` dosyasını indirip `/etc/tlp.conf` dosyası ile değiştirin.

```bash
gıt clone 
```

Yapılandırma değişikliklerini uygulamak için:

```bash
sudo tlp start
```

## Supergfxctl Kurulumu

Supergfxctl paketini kurun:

```bash
yay -S supergfxctl
```

## NVIDIA dGPU'yu Kapatma

Ayrık NVIDIA ekran kartını kapatıp yalnızca dahili ekran kartını kullanmak için:

```bash
sudo supergfxctl -m Integrated
```
## NVIDIA dGPU'yu Açma

Ayrık NVIDIA ekran kartını kullanmak için:

```bash
sudo supergfxctl -m Hybrıd
```

## İsteğe Bağlı: Supergfxctl Komutlarını sudo Olmadan Kullanma

Kullanıcınızı `games` grubuna ekleyin:

```bash
sudo usermod -aG games $USER
```

Değişikliğin uygulanması için oturumu kapatıp tekrar açın.

## Faydalı Supergfxctl Komutları

Mevcut ekran kartı modunu görüntüleme:

```bash
supergfxctl -g
```

Desteklenen ekran kartı modlarını görüntüleme:

```bash
supergfxctl -s
```



