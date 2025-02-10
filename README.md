# YouAreMyValentine-
    /* แผ่นเสียงหมุน */
    .record-container {
        position: relative;
        width: 200px;
        height: 200px;
        margin: 20px auto;
    }
    .record {
        width: 100%;
        height: 100%;
        background: url('https://cdn.pixabay.com/photo/2020/04/16/21/21/vinyl-5054260_1280.png') no-repeat center;
        background-size: cover;
        border-radius: 50%;
        animation: spin 4s linear infinite;
    }
    .record img {
        position: absolute;
        width: 80px;
        height: 80px;
        border-radius: 50%;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
    @keyframes spin {
        from { transform: rotate(0deg); }
        to { transform: rotate(360deg); }
    }
    .song-title {
        font-size: 18px;
        font-weight: bold;
        margin-top: 10px;
        color: white;
    }

    /* ข้อความเซอร์ไพรส์ */
    #message {
        font-size: 22px;
        font-weight: bold;
        color: white;
        margin-top: 20px;
        display: none;
    }

    /* เอฟเฟกต์หัวใจลอย */
    .heart {
        position: absolute;
        color: red;
        font-size: 24px;
        animation: floatUp 4s linear infinite;
    }
    @keyframes floatUp {
        0% {
            transform: translateY(0);
            opacity: 1;
        }
        100% {
            transform: translateY(-100vh);
            opacity: 0;
        }
    }

    /* เอฟเฟกต์ดาวตก */
    .shooting-star {
        position: absolute;
        width: 5px;
        height: 5px;
        background-color: pink;
        box-shadow: 0 0 8px pink;
        border-radius: 50%;
        animation: shootingStar 2s linear infinite;
    }
    @keyframes shootingStar {
        0% {
            transform: translate(100vw, -10vh);
            opacity: 1;
        }
        100% {
            transform: translate(-10vw, 100vh);
            opacity: 0;
        }
    }
</style>
