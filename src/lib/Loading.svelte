<div class="placeholder-item"></div>


<style>
  .placeholder-item {
    box-shadow: 0 4px 10px 0 rgba(33, 33, 33, 0.4);
    border-radius: 4px;
    height: 230px;
    position: relative;
    overflow: hidden;
    margin-top: 3rem;
}
.placeholder-item::before {
    content: '';
    display: block;
    position: absolute;
    left: -150px;
    top: 0;
    height: 100%;
    width: 150px;
    background: linear-gradient(to right, transparent 0%, #E8E8E8 50%, transparent 100%);
    animation: load 1s cubic-bezier(0.4, 0.0, 0.2, 1) infinite;
}
@keyframes load {
    from {
        left: -150px;
    }
    to   {
        left: 100%;
    }
}
</style>