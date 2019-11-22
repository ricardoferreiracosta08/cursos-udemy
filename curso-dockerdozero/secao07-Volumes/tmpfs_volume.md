tmpfs - persistindo dados em memória RAM (Linux)
============

* 01 - Criar container com dir mapeado em memória:
$>  sudo docker run -itd --name tmpfs --tmpfs /tmp busybox

* 02 - Mostrar particao RAM:
$>  sudo docker exec tmpfs df -h

* 03 - Criar arquivo com tamanho aproximado de memória reservada na partição do dir mapeado:
$>  sudo docker exec -it tmpfs busybox  dd if=/dev/zero of=/tmp/output bs=3k count=1000k; rm -f /tmp/output

* 04 - Criar arquivo com tamanho aproximado de memória reservada em outra partição do container:
$>  sudo docker exec -it tmpfs dd if=/dev/zero of=/output bs=3k count=1000k; rm -f /output




