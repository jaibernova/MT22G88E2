<template>
  <div id="SidebarApp">
    <ul
      class="navbar-nav bg-gradient-dark sidebar sidebar-dark accordion"
      id="accordionSidebar"
    >
      <!-- Sidebar - Brand -->
      <a
        class="sidebar-brand d-flex align-items-center justify-content-center"
        :href="'/information'"
      >
        <div class="sidebar-brand-icon rotate-n-15">
          <i class="fas fa-tools"></i>
        </div>
        <div class="sidebar-brand-text mx-3">FerreMax</div>
      </a>
      <!-- Divider -->
      <hr class="sidebar-divider my-0" />
      <!-- Nav Item - Dashboard -->
      <li class="nav-item active">
        <a class="nav-link" :href="'/information'">
          <i class="fas fa-fw fa-tachometer-alt"></i>
          <span>Dashboard</span></a
        >
      </li>
      <!-- Divider -->
      <hr class="sidebar-divider" />
      <!-- Heading -->
      <div class="sidebar-heading">Administrar Usuarios</div>
      <!-- Nav Item - Pages Collapse Menu -->
      <li class="nav-item">
        <a
          class="nav-link collapsed"
          :href="'/usuarios'"
          data-toggle="collapse"
          data-target="#collapseTwo"
          aria-expanded="true"
          aria-controls="collapseTwo"
        >
          <i class="fas fa-users-cog"></i>
          <span>Usuarios</span>
        </a>
        <div
          id="collapseTwo"
          class="collapse"
          aria-labelledby="headingTwo"
          data-parent="#accordionSidebar"
        >
          <div class="bg-white py-2 collapse-inner rounded">
            <a class="collapse-item" href="buttons.html">Registrar Usuarios</a>
          </div>
        </div>
      </li>
      <!-- Divider -->
      <hr class="sidebar-divider" />
      <!-- Heading -->
      <div class="sidebar-heading">Administrar Productos</div>
      <li class="nav-item">
        <a
          class="nav-link collapsed"
          :href="'/productos'"
          data-toggle="collapse"
          data-target="#collapseTwo"
          aria-expanded="true"
          aria-controls="collapseTwo"
        >
          <i class="fas fa-fw fa-cog"></i>
          <span>Products</span>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "AppSidebar",
};
</script>


<style scoped>
ul {
  height: 100vh;
}
</style>

