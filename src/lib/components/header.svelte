<header>
    <div class="header-left">
        <img src={LogoMobile} alt="logo">
        <h1>{data.boards[currentBoard].name}</h1>
        <img src={DownArrow} alt="down-arrow">
    </div>
    <div class="header-right">
        <button><img src={AddTaskButton} alt="add-task"></button>
        <button><img src={VertElips} alt="vert-elips"></button>
    </div>
</header>

<script>
    import LogoMobile from '../assets/logo-mobile.svg';
    import LogoLight from '../assets/logo-light.svg';
    import LogoDark from '../assets/logo-dark.svg';

    import DownArrow from '../assets/icon-chevron-down.svg';
    import VertElips from '../assets/icon-vertical-ellipsis.svg';
    import AddTaskButton from '../assets/icon-add-task-mobile.svg';

    export let data;
    export let currentBoard;
</script>