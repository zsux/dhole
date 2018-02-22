


rsync -azCH -e "ssh -oStrictHostKeyChecking=no -p 22" --delete /docker/jsde/dev/service/data/ 192.168.37.220:/docker/jsde/dev/service/data/

rsync -pazCH -e "ssh -oStrictHostKeyChecking=no -p 22" --delete /docker/zhongjie/dev/service/data/ 192.168.37.220:/docker/zhongjie/dev/service/data/
