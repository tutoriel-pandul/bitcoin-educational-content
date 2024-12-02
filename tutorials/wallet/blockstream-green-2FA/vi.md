---
name: Blockstream Green - 2FA
description: Cài đặt 2/2 multisig trên Green Wallet
---
![cover](assets/cover.webp)

Ví phần mềm là một ứng dụng được cài đặt trên máy tính, điện thoại thông minh, hoặc bất kỳ thiết bị nào khác có kết nối Internet, cho phép quản lý và bảo mật chìa khóa ví Bitcoin của người dùng. Khác với ví cứng, loại ví này không cô lập chìa khóa riêng tư, "ví nóng" do đó hoạt động trong môi trường có thể tiếp xúc với các cuộc tấn công mạng, tăng nguy cơ bị hack và mất cắp.

Ví phần mềm nên được sử dụng để quản lý số lượng bitcoins hợp lý, đặc biệt là cho các giao dịch hàng ngày. Đây cũng có thể là một lựa chọn thú vị cho những người có danh mục Bitcoin hạn chế, với họ việc đầu tư vào một ví cứng có vẻ không cân xứng. Tuy nhiên, việc tiếp xúc liên tục với Internet làm cho chúng kém an toàn hơn để lưu trữ tiết kiệm dài hạn hoặc số tiền lớn. Đối với những trường hợp này, nên chọn các giải pháp an toàn hơn, như ví cứng.

Trong hướng dẫn này, tôi sẽ chỉ bạn cách tăng cường bảo mật cho ví nóng bằng cách sử dụng tùy chọn "2FA" trên Blockstream Green.

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## Giới thiệu về Blockstream Green

Blockstream Green là một ví phần mềm có sẵn trên di động và máy tính để bàn. Trước đây được biết đến với tên *Green Address*, ví này trở thành một dự án của Blockstream sau khi được mua lại vào năm 2016.

Green là một ứng dụng đặc biệt dễ sử dụng, làm cho nó thú vị đối với người mới bắt đầu. Nó cung cấp tất cả các tính năng cần thiết của một ví Bitcoin tốt, bao gồm RBF (*Replace-by-Fee*), tùy chọn kết nối qua Tor, khả năng kết nối với node của riêng bạn, tùy chọn SPV (*Simple Payment Verification*), gắn nhãn, và kiểm soát coin.

Blockstream Green cũng hỗ trợ mạng Liquid, một sidechain của Bitcoin được phát triển bởi Blockstream để thực hiện các giao dịch nhanh chóng và bảo mật bên ngoài blockchain chính. Trong hướng dẫn này, chúng tôi chỉ tập trung vào Bitcoin, nhưng tôi cũng đã làm một hướng dẫn khác để học cách sử dụng Liquid trên Green:

https://planb.network/tutorials/wallet/blockstream-green-liquid

## Tùy chọn 2/2 multisig (2FA)

Trên Green, bạn có thể tạo một ví nóng "singlesig" cổ điển. Nhưng bạn cũng có tùy chọn "2FA multisig", cho phép bạn cải thiện bảo mật cho ví nóng của mình mà không làm phức tạp quá mức việc quản lý hàng ngày.
Bạn sẽ thiết lập một ví 2/2 multisig, nghĩa là mỗi giao dịch sẽ yêu cầu chữ ký của hai khóa. Khóa đầu tiên, được tạo từ cụm từ ghi nhớ 12 hoặc 24 từ của bạn, được bảo mật cục bộ bằng mã PIN trên điện thoại của bạn. Bạn có toàn quyền kiểm soát khóa này. Khóa thứ hai được giữ bởi máy chủ của Blockstream, và việc sử dụng nó để ký cần phải được xác thực, có thể được thực hiện qua mã nhận được qua email, SMS, cuộc gọi điện thoại, hoặc, như chúng ta sẽ thấy trong hướng dẫn này, qua một ứng dụng xác thực (Authy, Google Authenticator, v.v.).

Để đảm bảo sự tự chủ của bạn trong trường hợp Blockstream gặp sự cố (ví dụ, nếu công ty phá sản hoặc các máy chủ giữ khóa thứ hai bị hủy), một cơ chế khóa thời gian được áp dụng cho multisig của bạn. Cơ chế này biến 2/2 multisig thành 1/2 multisig sau khoảng một năm (hoặc chính xác là 51,840 khối, nhưng giá trị này có thể được thay đổi), sau đó ví của bạn chỉ cần khóa cục bộ của bạn để chi tiêu bitcoins. Như vậy, nếu bạn mất quyền truy cập vào máy chủ của Blockstream hoặc xác thực 2FA, bạn chỉ cần chờ đến một năm để có thể sử dụng tự do bitcoins của mình với ứng dụng của bạn, không phụ thuộc vào Blockstream.
![GREEN 2FA MULTISIG](assets/fr/02.webp)
Phương pháp này tăng cường đáng kể độ an toàn của ví nóng của bạn, đồng thời vẫn giữ cho bạn kiểm soát bitcoin của mình và hỗ trợ việc sử dụng hàng ngày. Tuy nhiên, nó đòi hỏi việc làm mới định kỳ khóa thời gian để duy trì độ an toàn của 2FA. Đếm ngược 360 ngày, trong khoảng thời gian mà tiền của bạn được bảo vệ bởi 2FA, bắt đầu ngay khi bạn nhận được bitcoin. Nếu, sau 360 ngày kể từ khi nhận chúng, bạn không thực hiện giao dịch chi tiêu số tiền đó, bitcoin của bạn chỉ được bảo vệ bởi khóa cục bộ của bạn, không có 2FA.

Ràng buộc này làm cho tùy chọn 2FA phù hợp hơn với một ví chi tiêu, nơi các giao dịch thường xuyên tự động làm mới các khóa thời gian. Đối với một ví tiết kiệm dài hạn, điều này có thể gây ra vấn đề, vì bạn cần phải nghĩ đến việc thực hiện một giao dịch quét cho chính mình mỗi năm trước khi khóa thời gian hết hạn.

Một nhược điểm khác của phương pháp bảo mật này là bạn sẽ cần sử dụng các mẫu script thiểu số. Điều này có nghĩa là, từ quan điểm về quyền riêng tư, mọi thứ trở nên phức tạp: rất ít người sử dụng cùng một loại script như bạn, cho phép một người quan sát bên ngoài dễ dàng xác định dấu vết ví của bạn hơn. Hơn nữa, những script này sẽ dẫn đến phí giao dịch cao hơn do kích thước lớn hơn.
Nếu bạn không muốn sử dụng tùy chọn 2FA và chỉ muốn thiết lập một ví "singlesig" trên Green, tôi mời bạn xem hướng dẫn khác này:
https://planb.network/tutorials/wallet/blockstream-green-liquid

## Cài Đặt và Thiết Lập Phần Mềm Blockstream Green

Bước đầu tiên tự nhiên là tải xuống ứng dụng Green. Truy cập cửa hàng ứng dụng của bạn:
- [Cho Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Cho Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN 2FA MULTISIG](assets/fr/03.webp)

Đối với người dùng Android, bạn cũng có tùy chọn cài đặt ứng dụng qua tệp `.apk` [có sẵn trên GitHub của Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN 2FA MULTISIG](assets/fr/04.webp)

Khởi chạy ứng dụng, sau đó đánh dấu vào ô "*Tôi chấp nhận các điều khoản...*".

![GREEN 2FA MULTISIG](assets/fr/05.webp)

Khi bạn mở Green lần đầu tiên, màn hình chính xuất hiện mà không có ví nào được cấu hình. Sau này, nếu bạn tạo hoặc nhập ví, chúng sẽ xuất hiện trong giao diện này. Trước khi chuyển sang tạo ví, tôi khuyên bạn nên điều chỉnh cài đặt ứng dụng theo mong đợi của bạn. Nhấp vào "*Cài Đặt Ứng Dụng*".

![GREEN 2FA MULTISIG](assets/fr/06.webp)

Tùy chọn "*Tăng Cường Quyền Riêng Tư*", chỉ có sẵn trên Android, cải thiện quyền riêng tư bằng cách vô hiệu hóa chụp màn hình và ẩn xem trước ứng dụng. Nó cũng tự động khóa quyền truy cập vào ứng dụng ngay khi điện thoại của bạn bị khóa, làm cho dữ liệu của bạn khó bị phơi bày hơn.

![GREEN 2FA MULTISIG](assets/fr/07.webp)

Đối với những ai muốn tăng cường quyền riêng tư, ứng dụng cung cấp tùy chọn định tuyến lưu lượng truy cập của bạn qua Tor, một mạng lưới mã hóa tất cả các kết nối của bạn và làm cho hoạt động của bạn khó theo dõi. Mặc dù tùy chọn này có thể làm chậm hiệu suất của ứng dụng một chút, nó được khuyến nghị cao để bảo vệ quyền riêng tư của bạn, đặc biệt nếu bạn không sử dụng full node của riêng mình.

![GREEN 2FA MULTISIG](assets/fr/08.webp)

Đối với người dùng có full node của riêng mình, Ví Green cung cấp khả năng kết nối với nó qua một máy chủ Electrum, đảm bảo kiểm soát đầy đủ thông tin mạng Bitcoin và phát sóng giao dịch.
![GREEN 2FA MULTISIG](assets/fr/09.webp)
Một tính năng thay thế khác là tùy chọn "*Xác minh SPV*", cho phép xác minh trực tiếp một số dữ liệu blockchain, giảm bớt nhu cầu phải tin tưởng vào nút mặc định của Blockstream, mặc dù phương pháp này không cung cấp tất cả các bảo đảm của một nút đầy đủ.
![GREEN 2FA MULTISIG](assets/fr/10.webp)
Sau khi điều chỉnh các cài đặt theo nhu cầu của bạn, nhấn vào nút "*Lưu*" và khởi động lại ứng dụng.

![GREEN 2FA MULTISIG](assets/fr/11.webp)

## Tạo Ví Bitcoin trên Blockstream Green

Bây giờ bạn đã sẵn sàng để tạo một ví Bitcoin. Nhấn vào nút "*Bắt đầu*".

![GREEN 2FA MULTISIG](assets/fr/12.webp)

Bạn có sự lựa chọn giữa việc tạo một ví phần mềm cục bộ hoặc quản lý một ví lạnh thông qua một ví cứng. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc tạo một ví nóng, vì vậy bạn sẽ cần chọn tùy chọn "*Trên Thiết Bị Này*".

![GREEN 2FA MULTISIG](assets/fr/13.webp)

Tiếp theo, bạn có thể chọn khôi phục một ví Bitcoin hiện có hoặc tạo một ví mới. Với mục đích của hướng dẫn này, chúng tôi sẽ tạo một ví mới. Tuy nhiên, nếu bạn cần tái tạo một ví Bitcoin hiện có từ cụm từ ghi nhớ của nó, ví dụ, do mất điện thoại cũ, bạn sẽ cần chọn tùy chọn thứ hai.

![GREEN 2FA MULTISIG](assets/fr/14.webp)

Sau đó, bạn có sự lựa chọn giữa một cụm từ ghi nhớ 12 từ hoặc 24 từ. Cụm từ này sẽ cho phép bạn khôi phục quyền truy cập vào ví của mình từ bất kỳ phần mềm tương thích nào trong trường hợp có vấn đề với điện thoại của bạn. Hiện tại, việc chọn một cụm từ 24 từ không cung cấp nhiều bảo mật hơn so với một cụm từ 12 từ. Do đó, tôi khuyên bạn nên chọn một **cụm từ ghi nhớ 12 từ**.

Green sau đó sẽ cung cấp cho bạn cụm từ ghi nhớ của mình. Trước khi tiếp tục, hãy chắc chắn rằng bạn không bị quan sát. Nhấn vào "*Hiển thị cụm từ khôi phục*" để hiển thị nó trên màn hình.

![GREEN 2FA MULTISIG](assets/fr/15.webp)

**Cụm từ ghi nhớ này cho phép truy cập hoàn toàn và không hạn chế vào tất cả bitcoin của bạn**. Bất kỳ ai sở hữu cụm từ này có thể ăn cắp tiền của bạn, ngay cả khi không có quyền truy cập vật lý vào điện thoại của bạn (trong trường hợp thời gian khóa hết hạn hoặc 2FA trong trường hợp của một ví 2/2 trên Green).

Nó cho phép bạn khôi phục quyền truy cập vào các khóa cục bộ trong trường hợp mất mát, trộm cắp, hoặc hỏng hóc điện thoại. Do đó, việc lưu trữ nó một cách cẩn thận **trên một phương tiện vật lý (không phải kỹ thuật số)** và bảo quản nó ở một nơi an toàn là rất quan trọng. Bạn có thể ghi nó ra một tờ giấy, hoặc để đảm bảo an toàn hơn, nếu ví này quan trọng, tôi khuyên bạn nên khắc nó trên một phương tiện bằng thép không gỉ để bảo vệ khỏi rủi ro của hỏa hoạn, lũ lụt, hoặc sụp đổ (đối với một ví nóng nhằm bảo vệ một lượng nhỏ bitcoin, một bản sao giấy đơn giản có lẽ là đủ).
*Rõ ràng, bạn không bao giờ nên chia sẻ những từ này trên internet, không giống như những gì tôi đang làm trong hướng dẫn này. Ví dụ này chỉ được sử dụng trên Testnet và sẽ được xóa ở cuối hướng dẫn.*
![GREEN 2FA MULTISIG](assets/fr/16.webp)

Sau khi ghi chính xác cụm từ ghi nhớ của bạn trên một phương tiện vật lý, nhấn vào "*Tiếp tục*". Ví Green sau đó sẽ yêu cầu bạn xác nhận một số từ từ cụm từ của bạn để kiểm tra xem bạn đã ghi chúng một cách chính xác hay không. Điền vào các ô trống với những từ còn thiếu.

![GREEN 2FA MULTISIG](assets/fr/17.webp)
Chọn mã PIN cho thiết bị của bạn, mã này sẽ được sử dụng để mở khóa ví Green của bạn. Do đó, đây là một biện pháp bảo vệ chống lại việc truy cập trái phép về mặt vật lý. Mã PIN này không tham gia vào quá trình tạo ra các khóa mật mã của ví bạn. Vì vậy, ngay cả khi không có quyền truy cập vào mã PIN này, việc sở hữu cụm từ ghi nhớ 12 hoặc 24 từ của bạn sẽ cho phép bạn lấy lại quyền truy cập vào các khóa cục bộ của mình.

Khuyến nghị chọn một mã PIN 6 chữ số càng ngẫu nhiên càng tốt. Ngoài ra, hãy chắc chắn lưu mã này để bạn không quên nó, nếu không, bạn sẽ buộc phải khôi phục ví của mình từ cụm từ ghi nhớ. Bạn có thể sau này thêm tùy chọn khóa sinh trắc học để tránh phải nhập mã PIN mỗi lần. Nói chung, sinh trắc học kém an toàn hơn nhiều so với chính mã PIN. Do đó, theo mặc định, tôi khuyên không nên thiết lập tùy chọn mở khóa này.

![GREEN 2FA MULTISIG](assets/fr/18.webp)

Nhập lại mã PIN một lần nữa để xác nhận.

![GREEN 2FA MULTISIG](assets/fr/19.webp)

Chờ trong khi ví của bạn đang được tạo, sau đó nhấp vào nút "*Tạo một tài khoản*".

![GREEN 2FA MULTISIG](assets/fr/20.webp)

Sau đó, bạn có lựa chọn giữa một ví chữ ký đơn tiêu chuẩn hoặc một ví được bảo vệ bởi xác thực hai yếu tố (2FA). Trong hướng dẫn này, chúng tôi sẽ chọn lựa chọn thứ hai.

![GREEN 2FA MULTISIG](assets/fr/21.webp)

Và đó là, ví multisig Bitcoin của bạn đã được tạo thành công bằng ứng dụng Green!

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## Thiết lập 2FA

Nhấp vào tài khoản của bạn.

![GREEN 2FA MULTISIG](assets/fr/23.webp)

Nhấp vào nút xanh "*Tăng cường bảo mật cho tài khoản của bạn bằng cách thêm 2FA*".

![GREEN 2FA MULTISIG](assets/fr/24.webp)
Sau đó, bạn sẽ có tùy chọn chọn phương thức xác thực để truy cập vào khóa thứ hai của ví 2/2 multisig của bạn. Trong hướng dẫn này, chúng tôi sẽ sử dụng một ứng dụng xác thực. Nếu bạn không quen với loại ứng dụng này, tôi khuyên bạn nên tham khảo hướng dẫn của chúng tôi về Authy:
https://planb.network/tutorials/others/authy

Chọn "*Ứng dụng Xác thực*".

![GREEN 2FA MULTISIG](assets/fr/25.webp)

Green sau đó sẽ hiển thị một mã QR và một khóa khôi phục. Khóa này cho phép bạn khôi phục quyền truy cập vào 2FA của mình trong trường hợp bạn mất ứng dụng Authy. Khuyến nghị làm một bản sao lưu an toàn của khóa này, mặc dù bạn luôn có thể lấy lại quyền truy cập vào bitcoin của mình sau khi thời gian khóa hết hạn, như đã giải thích trước đó.

Trong ứng dụng xác thực của bạn, thêm một mã mới, sau đó quét mã QR do Green cung cấp.

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*Rõ ràng, bạn không bao giờ nên chia sẻ khóa này và mã QR trên internet, trái ngược với những gì tôi đang làm trong hướng dẫn này. Ví dụ này chỉ được sử dụng trên Testnet và sẽ được xóa vào cuối hướng dẫn.*

Nhấp vào nút "*Tiếp tục*".

![GREEN 2FA MULTISIG](assets/fr/27.webp)

Nhập mã 6 chữ số động hiện trên ứng dụng xác thực của bạn.

![GREEN 2FA MULTISIG](assets/fr/28.webp)

Xác thực hai yếu tố giờ đây đã được kích hoạt.

![GREEN 2FA MULTISIG](assets/fr/29.webp)
Khi duyệt qua menu này, bạn cũng có thể điều chỉnh thời gian của khóa thời gian (timelock). Đếm ngược này bắt đầu khi nhận bitcoin, và một khi khóa thời gian hết hạn, số tiền của bạn chỉ có thể được chi tiêu bằng khóa địa phương của bạn, không yêu cầu xác thực 2 yếu tố (2FA). Thời gian mặc định được thiết lập là 12 tháng, nhưng đối với một ví tiết kiệm, việc chọn 15 tháng có thể là sáng suốt để giảm tần suất gia hạn khóa thời gian. Ngược lại, đối với một ví chi tiêu, một khóa thời gian 6 tháng có thể được ưa chuộng, vì nó sẽ được gia hạn thường xuyên với các giao dịch hàng ngày của bạn, và một khóa thời gian ngắn hơn giảm thời gian chờ đợi trong trường hợp có vấn đề với 2FA. Quyết định thời gian khóa thời gian phù hợp nhất với bạn là do bạn.

Bạn có thể thoát khỏi menu này. Ví đa chữ ký của bạn đã sẵn sàng!

## Thiết lập ví của bạn trên Blockstream Green

Nếu bạn muốn tùy chỉnh ví của mình, hãy nhấp vào ba chấm nhỏ ở góc trên bên phải.

Tùy chọn "*Đổi tên*" cho phép bạn tùy chỉnh tên của ví, điều này đặc biệt hữu ích nếu bạn quản lý nhiều ví trên cùng một ứng dụng.

Menu "*Đơn vị*" cho bạn lựa chọn thay đổi đơn vị cơ bản của ví. Ví dụ, bạn có thể chọn hiển thị nó bằng satoshis thay vì bitcoins.

Menu "*Cài đặt*" cung cấp quyền truy cập vào các tùy chọn khác nhau của ví Bitcoin của bạn.

Tại đây, ví dụ, bạn sẽ tìm thấy khóa công khai mở rộng của mình và *mô tả* của nó, hữu ích nếu bạn dự định thiết lập một ví chỉ xem từ ví này.

Bạn cũng có thể thay đổi mã PIN của ví và kích hoạt đăng nhập sinh trắc học.

## Sử dụng Blockstream Green

Bây giờ ví Bitcoin của bạn đã được thiết lập, bạn đã sẵn sàng để nhận sats đầu tiên của mình! Để làm điều này, chỉ cần nhấp vào nút "*Nhận*".

Green sau đó sẽ hiển thị địa chỉ nhận trống đầu tiên của ví bạn. Bạn có thể quét mã QR liên kết hoặc sao chép địa chỉ trực tiếp để gửi bitcoin đến nó. Loại địa chỉ này không chỉ định số tiền cần gửi bởi người thanh toán. Tuy nhiên, bạn có thể tạo một địa chỉ yêu cầu một số tiền cụ thể, bằng cách nhấp vào ba chấm nhỏ ở góc trên bên phải, sau đó chọn "*Yêu cầu Số Tiền*", và nhập số tiền mong muốn.

Khi giao dịch được phát sóng trên mạng, nó sẽ xuất hiện trong ví của bạn.

Chờ đợi để nhận đủ xác nhận để coi giao dịch là cuối cùng.

Với bitcoin trong ví của bạn, bây giờ bạn cũng có thể gửi chúng. Nhấp vào "*Gửi*".

Trên trang tiếp theo, nhập địa chỉ của người nhận. Bạn có thể nhập nó thủ công hoặc quét mã QR.

Chọn số tiền thanh toán.
![GREEN 2FA MULTISIG](assets/fr/44.webp)Ở phía dưới màn hình, bạn có thể chọn mức phí cho giao dịch này. Bạn có lựa chọn tuân theo khuyến nghị của ứng dụng hoặc tự tùy chỉnh phí của mình. Mức phí càng cao so với các giao dịch đang chờ khác, giao dịch của bạn sẽ được xử lý nhanh hơn. Để hiểu về thị trường phí, bạn có thể truy cập [Mempool.space](https://mempool.space/) trong mục "*Phí Giao Dịch*".
![GREEN 2FA MULTISIG](assets/fr/45.webp)

Nhấn vào "*Tiếp theo*" để truy cập màn hình tổng kết giao dịch của bạn. Kiểm tra xem địa chỉ, số lượng và phí có chính xác không.

![GREEN 2FA MULTISIG](assets/fr/46.webp)

Nếu mọi thứ đều ổn với bạn, hãy trượt nút màu xanh ở phía dưới màn hình sang phải để ký và phát sóng giao dịch trên mạng Bitcoin.

![GREEN 2FA MULTISIG](assets/fr/47.webp)

Đây là lúc bạn cần nhập mã xác thực để mở khóa chìa khóa thứ hai của multisig được giữ bởi Blockstream. Nhập mã 6 chữ số hiển thị trên ứng dụng xác thực của bạn.

![GREEN 2FA MULTISIG](assets/fr/48.webp)

Giao dịch của bạn giờ đây sẽ xuất hiện trên bảng điều khiển của ví Bitcoin của bạn chờ được xác nhận.

![GREEN 2FA MULTISIG](assets/fr/49.webp)

Và đó là tất cả, bạn giờ đây đã biết cách dễ dàng thiết lập một ví multisig 2/2 sử dụng tùy chọn 2FA của Blockstream Green!

Nếu bạn thấy hướng dẫn này hữu ích, tôi sẽ rất biết ơn nếu bạn có thể để lại một ngón tay xanh phía dưới. Đừng ngần ngại chia sẻ bài viết này trên các mạng xã hội của bạn. Cảm ơn bạn rất nhiều!

Tôi cũng khuyên bạn nên xem hướng dẫn hoàn chỉnh khác về ứng dụng di động Blockstream Green để thiết lập một ví Liquid:

https://planb.network/tutorials/wallet/blockstream-green-liquid