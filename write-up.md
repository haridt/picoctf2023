# Reverse
Đầu tiên mở file bằng ida lên, chúng ta sẽ kiểm tra xem flag có ở trên strings không. May mà có , nên đỡ cực :))

![image](https://github.com/haridt/nasm/assets/131541155/88a4132f-7aa1-4c66-8495-1e6ffa673444)

->>FLAG: ``` picoCTF{3lf_r3v3r5ing_succe55ful_2f0131a4} ```

# Safe Opener 2
Mở file bằng ida lên, kéo xuống tí là thấy code 

![image](https://github.com/haridt/picoctf2023/assets/131541155/40427a86-3a24-40c4-90ea-72968fd15e54)

->>FLAG:``` picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_3dae8463}```

# Timer
Mở file bằng ida lên( lag kinh khủng), vào strings bấm ctr +f kiếm pico là ra( thề nhiều lệnh vcl, lag kinh)

![image](https://github.com/haridt/picoctf2023/assets/131541155/93490327-3147-4cd2-b800-f31b408c852e)



->>FLAG: ```picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}```

# Ready Gladiator 0
Đầu tiên ta sẽ sửa file imp.red: ```;redcode ;name Imp Ex ;assert 1 mov 0, -1 end```
Sau đó ta nhập ` nc saturn.picoctf.net 58626 < imp.red ` (theo đề bài cho)
trên terminal(hoặc WLS) thì sẽ hiện flag

![image](https://github.com/haridt/picoctf2023/assets/131541155/33b2086f-63f9-4d46-848d-d5d392ff30d1)

->>FLAG:``` picoCTF{h3r0_t0_z3r0_4m1r1gh7_e1610ed2}```

# Ready Gladiator 1
Chúng ta sẽ lại sửa đoạn code để tìm flag lần nữa, chúng ta sẽ copy đoạn code past trên gg để tìm ra đoạn code phù hợp để chạy ctr. Và đây là đoạn code t tìm đc 
```
;redcode
;name Paper-Scissors-Rock
;assert 1

sub 1, -10
jmp -1

end
```
Sau khi sửa file, chúng ta lại dùng terminal(hoặc WLS) và kết nối server bằng dòng chữ đỏ trên đề bài. Sau khi kết nối sẽ hiện flag.

![image](https://github.com/haridt/picoctf2023/assets/131541155/4bb85cae-c246-490f-84ab-6f10370cf86c)


->>FLAG: ```picoCTF{1mp_1n_7h3_cr055h41r5_441be1fc}```

# Ready Gladiator 2
Tương tự như 2 bài trên, chúng ta lại sẽ sửa đoạn code nhưng lần này phải đạt số điểm 100. Thì mình cũng tham khảo từ gg đc đoạn code này
``` ;redcode-94nop
;name frenzy v6
;author Lukasz Grabun
;assert 1
		org	boot

step		equ	3000

start		add	#step+step,2
		mov	bomb,	@1
		mov	bomb,	@1
cl		jmp	-3,	>-8		;hit to start clear
		mov	dbomb,	>start-4
		djn.f	-1,	>start-4
dbomb		dat.f	<5334,	dbomb-start+7
bomb		spl	#0,	#step

for 83
		dat	0,	0
rof

boot		mov	bomb,	2000
for 7
		mov	{boot,	<boot
rof
		jmp	@boot,	<-1000

end
```
Sau khi run sẽ tìm đc flag
->>FLAG: ``` picoCTF{d3m0n_3xpung3r_9a074a57}```








